# Kevin Wu - Lab Report 2
# Servers and Bugs
This page discusses the processes of starting a web server and analysis of bugs.

## Part 1 StringServer:
### StringServer Code:

*Code for StringServer main method*

<img width="625" alt="Screenshot 2023-01-27 at 11 34 59 AM" src="https://user-images.githubusercontent.com/115754187/215181224-0e5fa31a-8dda-4067-9868-bc6c5d64251b.png">

*Code for Handler method*

<img width="616" alt="Screenshot 2023-01-27 at 11 34 38 AM" src="https://user-images.githubusercontent.com/115754187/215181152-a155582c-92bb-4ad1-8134-8527f238c41d.png">



**Default Page Screen and Message:**

<img width="365" alt="Screenshot 2023-01-27 at 11 37 02 AM" src="https://user-images.githubusercontent.com/115754187/215181602-fe04fbe9-f2d2-4b74-b318-6fd2be290116.png">

* Main method in StringServer runs and starts a server on port 4000. 
* (Server class reused from Week 2, provided by the teacher). 
* With "new Handler()" as a parameter for "Server.start," Handler object is created. 
* handleRequest method is called, first if condition is true, welcome message is displayed.


**First time going to "/add-message" path**

<img width="501" alt="Screenshot 2023-01-27 at 11 37 21 AM" src="https://user-images.githubusercontent.com/115754187/215181660-109c8718-5523-4b01-8eb0-fa06558d14ca.png">

* *handleRequest* method is called, first if condition is false. 
* Goes to else bracket, prints out path to the console. 
* Checks that the path contains *"/add-message"*. 
* Splits the query, *"s=Hello"* by the "=" and puts into an array, *parameters*. 
* Checks the first item, parameter[0], is equal to "s". 
* Adds the string, parameters[1], to the empty string in the instance variable **container** along with a newline character. 
* Returns the string variable **container** to be displayed on the web server.


**Second time**

<img width="596" alt="Screenshot 2023-01-27 at 11 37 37 AM" src="https://user-images.githubusercontent.com/115754187/215181708-3328cd79-d940-45e1-b7c4-c57c81638442.png">

* handleRequest method is called, first if condition is also false
* Goes to else bracket, prints out path to the console
* Checks that the path contains *"/add-message"*
* Splits the query, *"s=How%20are%20you"*, by the "=" into an array, *parameters*
* Adds the string, parameters[1], to **container** along with a newline character 
* (Variable **container** here is updated, now contains *"Hello\nHow%20are%20you"*)
* Returns the string variable **container** to be displayed on the web server

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Part 2 Bugs
Infinite Loop Bug from List Methods:

### Merge method from ListExamples.java
**Before:**
```
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      ** index1 += 1; **
    }
    return result;
  }
```

**After:**
```
static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      ** index2 += 1; **
    }
    return result;
  }
```

**Failure-Inducing Input (JUnit Test):**
(This is within ListTests.java file)
```
    @Test
    public void testMerge1(){
        ArrayList<String> list1 = new ArrayList<>();
        ArrayList<String> list2 = new ArrayList<>();
        list1.add("book");
        list1.add("dog");
        list2.add("apple");
        list2.add("hello");
        list1.add("evening");

        assertArrayEquals(new String[]{"apple", "book", "dog", "evening", "hello"}, ListExamples.merge(list1, list2).toArray());
    }
```
  > This fails because there are more than two items in list two. The second item in the list2, "hello," will never get appended to the new list due to the infinite loop.

**Non-Failure-Inducing Input (JUnit Test):**
(This is within ListTests.java file)
```
    @Test
    public void testMerge2(){
        ArrayList<String> list1 = new ArrayList<>();
        ArrayList<String> list2 = new ArrayList<>();
        list1.add("book");
        list1.add("dog");
        list2.add("apple");
        list1.add("evening");
        list1.add("hello");

        assertArrayEquals(new String[]{"apple", "book", "dog", "evening", "hello"}, ListExamples.merge(list1, list2).toArray());
    }
```
  > Because the very first alphabetical string is "apple" is in list2 and it is the only string in the list. Once that first gets appended to the new list, index2 counter is increased. Every instance of index2 < list2.size() would return false (1 < 1 is not true). Index1 is updated everywhere else, so there is no risk of encountering an infinite loop with this input.

**Symptom:**
<img width="988" alt="Screenshot 2023-01-27 at 2 30 33 PM" src="https://user-images.githubusercontent.com/115754187/215218517-eadd04ad-2e9f-4982-a311-c055a4d16121.png">

> Changing the *index1 += 1;* to *index2 += 1;* fixes the bug. Without index2 increasing in count, the very last while loop would cause an infinite loop. If index2 was already less than list2.size(), then that statement always returns true. Previously, when index1 += 1 was in the code, nothing was making sure that the program would exit the while loop at some point, thus, creating an infinite loop. Java denotes this as **java.lang.OutOfMemoryError**.
> 

----------------------------------------------------------------------------------------------------------------------------------------------------------

## Part 3 Takeaway:
I learned how to create a web server in Java from week 2. I thought that it was very interesting how simple it can be to display a simple message on a screen through Jawa. You are able to check if there's a query, and through that query, you can add that message to the screen along with all the previous messages. I am interested to look more into the possibilities that this opens up for me in terms of self-exploration. 



## END
