# Kevin Wu - Lab Report 4

## 1.(Setup) Delete any existing forks of the repository you have on your account

![step1](https://user-images.githubusercontent.com/115754187/221067155-689a62e9-4eea-4af0-9f74-b564bbe2f850.jpeg)

> I logged into my GitHub account, went to my existing lab7 repository that I forked previously, clicked "Settings" in the navbar above, scrolled down to where it says "Delete this repository" and click it. 

## 2.(Setup) Fork the repository

![step 2 part1](https://user-images.githubusercontent.com/115754187/221067240-bd4c6f2f-c8c8-4e26-80a0-f9a1947da932.jpeg)

![step 2 part 2](https://user-images.githubusercontent.com/115754187/221067257-e05cb690-8c74-4f7d-a129-b208fc9a9baf.jpeg)

> Click "Fork" on the upper right, then "Create Fork" on the bottom. 

## 3.Log into ieng6

![Screenshot 2023-02-23 at 4 59 44 PM](https://user-images.githubusercontent.com/115754187/221067412-f784d132-8c05-4c68-b1f5-6c5f134ceec8.jpeg)

> I logged into my ieng6 machine by typing in "ssh cs15lwi23age@ieng6.ucsd.edu" in the terminal.

## 4.Clone your fork of the repository from your Github account

![Screenshot 2023-02-23 at 5 00 09 PM](https://user-images.githubusercontent.com/115754187/221067456-f4d690a9-880a-4946-baa1-58fa39ee7a43.jpeg)
![step4 part2](https://user-images.githubusercontent.com/115754187/221067531-bc9e5616-2520-4c84-9cc9-5cd09598bbb4.jpeg)

> On my repository that I forked, I clicked the green button that says "CODE" and clicked "SSH", clicked the two squares button next to the link to copy the link.
> In my terminal on VSCode, I typed in "git clone git@github.com:kevwu27/lab7.git" and pressed <Enter>
 
## 5.Run the tests, demonstrating that they fail
  
![Screenshot 2023-02-23 at 11 41 15 PM](https://user-images.githubusercontent.com/115754187/221120993-c9d28ebb-1450-4943-a3a6-32031d40a9ee.jpeg)

> I typed "cd lab7", then <CNTRL-R>, and then I typed "javac" and hit enter to run "javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java"
> I typed <CNTRL-R> again and then I typed "java " (with the space) and hit enter to run "java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests".
> These commands worked because they were in my history of commands since I have used them before. 

## 6.Edit the code file to fix the failing test
  
![Screenshot 2023-02-23 at 5 32 41 PM](https://user-images.githubusercontent.com/115754187/221119204-2f7f5e20-0224-4e52-90b9-fd8aa0931a07.jpeg)

> I typed "nano ListExamples.java" into the terminal and hit enter.
> Then, I pressed <CNTRL-W> and then entered "index1 += 1", hit <Enter>, then hit <down> 12 times, then <right> 4 times in order to access the third "index1 += 1" as that is where the error occurred..
> Then, I deleted the '1' character in index1 and replaced it with '2'
> Then, I pressed <CNTRL-O> and then <Enter> to save the changes to the file.
> Then, I pressed <CNTRL-X> to exit out of nano.

## 7.Run the tests, demonstrating that they now succeed
  
 ![Screenshot 2023-02-23 at 11 41 50 PM](https://user-images.githubusercontent.com/115754187/221120952-f1b640b7-e5a4-413c-af1d-73d4b5c42e6e.jpeg)

> I then hit <CNTRL-R>, and then I typed "javac" and hit enter to run "javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java" to recompile files.
> I typed <CNTRL-R> again and then I typed "java<Space>" and hit enter to run "java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests".
> Again, these commands worked because they were in my history of commands since I have used them before.   
  

## 8.Commit and push the resulting change to your Github account

  ![Screenshot 2023-02-23 at 11 45 46 PM](https://user-images.githubusercontent.com/115754187/221121598-b64d7546-e220-40ec-81a3-05ebfdb9799f.jpeg)
  
> In the terminal, I typed "git add ListExamples.java" to add the file to the list of files needed to be pushed.
> Then, I typed "git commit -m "Updated"" to commit the changes to GitHub with the message "Updated".
> Finally, I typed "git push origin main" to push the changes to the forked repository from the remote server.
