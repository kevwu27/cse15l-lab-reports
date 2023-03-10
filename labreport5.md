# Kevin Wu - Lab Report 5: Recreating Lab Report 4 but With a Bash Script
This page shows how to create a bash script for the tasks involved in Lab Report 4.

## Setting up Computer and ieng6 Account
The first thing I did was set up my computer and create two bash scripts. A very important step is setting up SSH keys for the ieng6 machine. Following the steps of Week 7, I had set up SSH keys for my ieng6 account so that everytime I ssh into the account, I am not prompted for my passport on my local device, my MacBook laptop. 

Next, the task that I will attempt to complete using bash scripts is as follows: 
* Logging into ieng6 machine
* Cloning the repository 
* Running the tests, demonstrating that they fail
* Edit the code to fix the error
* Rerun the tests, demonstrating that they succeed
* Commit and push changes to my GitHub account

## Creating `setup.sh` file
On my local computer, I opened up VSCode and opened up an empty folder, named `labreport5`, but the name doesn't matter for this exercise. In it I created two files, one named `setup.sh` and the other named `task.sh`. I will edit task.sh later. First, I am going to put the following code into setup.sh.

![Screenshot 2023-03-09 at 6 19 37 PM](https://user-images.githubusercontent.com/115754187/224206689-5e5da1c3-a4d6-42b7-bbf9-78b6c44451ae.jpeg)

`scp task.sh cs15lwi23age@ieng6.ucsd.edu:~/`
> This command copies the task.sh that I will edit later that contains all the necessary commands for running through these tasks.

`ssh cs15lwi23age@ieng6.ucsd.edu`
> This command logs me into the ieng6 account. This allows me to log in without having to type the entire command and username out.

## `task.sh` file
This bash script is going to contain the actual commands needed to complete the tasks. In it, I have the following code: 

![Screenshot 2023-03-09 at 6 30 43 PM](https://user-images.githubusercontent.com/115754187/224208135-560381bf-7586-4724-960a-90462925e2fd.jpeg)

`rm -rf lab7`
> This command removes any existing repositories that have already been cloned onto the ieng6 machine. 

`git clone $1`
> This command clones the given repository. 
> The $1 is a bash variables, so when running task.sh, I need to make sure that I provide a ssh link for the GitHub repository that I am cloning.

`cd lab7`
> This command makes sure that I am on the right directory after cloning the repository. I need to be in the lab7 directory to be able to access the files.

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
> This command compiles all java files in the directory. 

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
> This command runs the tester file. After running this command, it will show that one test failed the first time. 

`sed -i -e '43 s/index1/index2/' ListExamples.java`
> This command, `sed`, goes into the ListExamples.java file and changes the `index1` on line 43 to `index2`. The modifiers, `-i and -e` make sure that 
> the command actually edits the file and saves it. 

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
> This command recompiles all java files in the directory. 

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
> This command reruns the tester file. Now, after running this command, it will show that all tests passed.

`git add ListExamples.java`
> This command adds the newly edited file, ListExamples.java, to the list of files needed to be committed and pushed to the GitHub account. 

`git commit -m "Updated"`
> This command commits the changes to GitHub with the message "Updated"

`git push origin main`
> This command pushes the changes to the forked repository from the remote server.

## Actually Running it
Before starting the timer, I go to the lab7 repository linked on the Week 7 lab and forked a new repository. I made sure to delete the one 
I had on my account previously. 

![Screenshot 2023-03-09 at 7 47 23 PM](https://user-images.githubusercontent.com/115754187/224218545-239022b0-efa5-43c1-b05f-afd14313ab19.jpeg)


After forking the repository, I made sure to copy the SSH link for it. It's important to copy the SSH link because I will be on the remote server, 
not my local device. Make sure that you have the link copied so that you can paste it quickly. 

![Screenshot 2023-03-09 at 7 49 06 PM](https://user-images.githubusercontent.com/115754187/224218819-b1c2f21e-c95c-4044-85a5-22df545bd33a.jpeg)


Now we can begin the tasks and start timing ourselves.
* Go in the terminal for VSCode where you have the bash scripts saved and type `setup.sh`. This will log you into the ieng6 machine and copy over the task.sh script. 
* Once logged in, type in `bash task.sh <CNTRL> + <V>` to paste in the link to the repository that you copied.
* All tasks should run properly! 


![Screenshot 2023-03-09 at 7 56 23 PM](https://user-images.githubusercontent.com/115754187/224219746-20cdd5ed-d80c-42b6-b5a8-db5fe2753166.jpeg)

![Screenshot 2023-03-09 at 7 56 43 PM](https://user-images.githubusercontent.com/115754187/224219749-25be2c1a-34dc-4a8c-a61c-408f0f1f0c0b.jpeg)


During lab and typing the actual commands in, it took me about 50 seconds to run through everything. 
However, with the bash scripts, I took only about 15 seconds. Most of the time was just waiting for the system to log in and run the commands.
I would say me typing in the terminal only took about 3 seconds. If we don't count the time of logging into the ieng6, then it would be even faster! 


The following screenshot shows that `sed` actually did edit the java file:

![Screenshot 2023-03-09 at 8 00 35 PM](https://user-images.githubusercontent.com/115754187/224220144-1bc2e032-d3cf-48cb-b20b-c65fc59d7d2f.jpeg)


This showed me that writing bash scripts can be very helpful and when used efficiently, can shave off a lot of time in the work that I do, 
especially if it is a tedious task. 

---
# END 

