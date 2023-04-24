# Lab Report 1 
> I am going to attempt to create a tutorial for incoming 15L studens to log into course specific accounts like `ieng6`

I will be covering:
1. Installing VScode
2. Remotely Connecting
3. Trying some Commands

## Installing VScode


Install Visual Sutio Code with the provided link below, and follow the steps to install. 

[Visual Studio Code]("https://code.visualstudio.com/")

Once you finish installing VScode, open the application. You should see a screen like this.

<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-04-06%20182625.png"  width="800"/>


## Remotely Connecting


Open a new terminal on VS Code by using the built-in terminal/command prompt or by simply uing ctrl + shift + ` 


Then type the follwing int your command prompt:

```
ssh <username + @ieng6-202.ucsd.edu>
```

  
Be sure to replace <username> with **your** username.

once you have types that, press enter.

You should see something like the following:

<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-04-10%20212234.png" width="900" />


You will see the yes/no option question in the terminal.
Type **yes**, and click enter.
Then retype what you frst wrote in the command prompt; this should prompt you to enter your password. 


Once you have entered your password, you should see a screen like this.


<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-04-10%20213256.png" width="900"/>

If you see a page like this, congrats!  You're in. 

## Trying some Commands
Let's try out some commands, here are a few examples we can try:
```
- cd ~
- cd
- las -lat
- ls <directory\>
- cp <directory\>
- cat <directory\>
```
  
Here is an example of how to type them if you are stuck:


<img src="https://github.com/namaldonado/cse15l-lab-reports/blob/main/Screenshot%202023-04-10%20214124.png"/>

  **To log out of the remote server in your terminal, you can use:**
* Ctrl-D
* Run the command `exit`
