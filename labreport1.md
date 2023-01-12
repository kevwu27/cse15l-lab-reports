# Kevin Wu - Lab Report 1
# Remote Access Tutorial
This page will detail how to remotely access *ieng6* (computers in CS) on your personal computer. 

## Step 1: Set Up
First download VSCode on your computer or open VSCode if you already have it. I already have VSCode, so I did not need to download it. However, if you need to download it, make sure to download the correct version according to your computer system (i.e. Windows or MacOC).

  >If you need to download VSCode, click this link:
  >[Link]( https://code.visualstudio.com/)
  >Then, open VSCode.
  
  Refer to Image Below for how VSCode should look when opened:
  *Note: Your VSCode may slightly differ, or have less file names on it. I have used VSCode before, which is why it shows my history of files.*
<img width="1440" alt="Screenshot 2023-01-12 at 10 20 15 AM" src="https://user-images.githubusercontent.com/115754187/212161406-460f2aac-47e6-4c19-a600-cd0d56e3a215.png">

   --------------------------------------------------------------------------------------------------------------------------------------------------

## Step 2: Remote Access
Next, I connected to the remote servers.

  1. Have VSCode open
  2. Open a new terminal (on Mac, hover your mouse to the top of the screen and click on *Terminal* then *New Terminal*
  3. If you are Windows, you will need to download Git. However, I'm on a Mac system, so I did not need to download Git, as it already comes with it.
  4. I typed in `ssh cs15lwi23age@ieng6.ucsd.edu` into the terminal. (This command is user specific)
  5. It prompted me to authenticate connecting, so I typed in *Yes*. Then I entered my password in and pressed enter.
  6. The following message should appear: 
  <img width="595" alt="Screenshot 2023-01-12 at 11 32 48 AM" src="https://user-images.githubusercontent.com/115754187/212163530-a2dc1b04-3378-46b1-bf28-df1d12f69317.png">
  
Now, I am remotely connected to the servers in the CSE basement!

   --------------------------------------------------------------------------------------------------------------------------------------------------

## Step 3: Trying Some Commands
Finally, I tested out some commands into the terminal.

  I typed the followings commands, in order.
  * `cd ~ `
  * `cd`
  * `ls -lat`
  * `ls -a`
  * `ls /home/linux/ieng6/cs15lwi23/cs15lwi23agd` (Me trying to access a group member's directory, resulted in permission denied)
  * `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
  * `cat /home/linux/ieng6/cs15lwi23/public/hello.txt` (Printed out "Hello! Welcome to CSE 15L")

The following results appeared in my terminal:
<img width="942" alt="Screenshot 2023-01-12 at 11 42 37 AM" src="https://user-images.githubusercontent.com/115754187/212165727-75da5cf3-441f-4a87-a8ee-e2b1d3f7c74c.png">

To exit out of the servers, I pressed *Control+D* on my computer and typed *exit* into the terminal.
  


