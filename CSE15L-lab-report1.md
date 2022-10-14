**Installing VScode**
* Go to the website https://code.visualstudio.com to download VScode
* Install it to my computer
* After successfully installing VScode, we should be able to open it and see a window like this below. 
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-09-30%20at%202.40.31%20PM.png)

**Remotely Connecting**
* Open a new terminal
* Type in the command: `ssh cs15lfa22kr@ieng6.ucsd.edu`
* Type in the password
* Successfully connected to the server
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-09-30%20at%202.47.54%20PM.png)

**Trying Some Commands**

In the image below, I tried some commands.
* ls: list the files in the directory
* ls -a: list all visible and hidden files in the directory
* ls -lat: list all visible and hidden files, including some information about the files
* pwd: print working 
* cat: print the contents of files
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-09-30%20at%202.55.35%20PM.png)

**Moving files with scp**
* Create a file called WhereAmI.java on the local computer 
* Use javac and java commands to run the program
* Use the command: `scp WhereAmI.java cs15lfa22kr@ieng6.ucsd.edu:~/`
* WhereAmI.java file is copied to the remote computer
* Log into the remote computer
* Use javac and java commands to run WhereAmI.java
* Get a different result from running on the local computer
![Image]https://github.com/catherineytf/cse15l-lab-reports/commit/5b41e4b1ab4d90d60a79b1d0191db2a1a4839235

**Setting an SSH Key**
* Command: ssh-keygen
* Log into the remote computer using ssh
* Make a new directory using mkdir .ssh
* Use scp on the local computer: `scp /Users/tongfeiyang/.ssh/id_rsa.pub cs15lfa22kr@ieng6.ucsd.edu:~/.ssh/authorized_keys`
* After these steps, we should be able to log into the remote computer without typing in the password
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-09-30%20at%201.40.00%20PM.png)

**Optimizing Remote Running**
* To optimize remote running, we can use up arrow to get `ssh cs15lfa22kr@ieng6.ucsd.edu` to reduce keystrokes.
* Then use scp command to update the local file to remote
* After updating the file, we can use semicolons to run multiple commands at the same time, which can also help reduce keystrokes. 
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-09-30%20at%202.40.14%20PM.png)

