# Lab Report1 1: Setting Up for CSE 15L

Welcome to CSE 15L! In this tutorial, we will be going over how to
log into a course-specifc account on 'ieng6'. There are three important 
steps to take in order to set up your environment, gain remote access, and
practice using commands.

* Install VScode
* Remotely Connect
* Using commands

## Part 1: Installing Visual Studio Code

1. To set up the environment, go to the Visual Studio Code website: [Link](https://code.visualstudio.com/), and follow the instructions to download and
install it onto your device. This can be done with all versions of operating systems
like OSX and Windows.

2. Once installed, open VSCode and a window should open to the interface of the text editor. 
It may appear with different colors or a menu bar based on your system and settings:

<img width="500" alt="Screenshot 2023-01-12 at 1 51 41 PM" src="https://user-images.githubusercontent.com/122497165/212190989-5e3bde1d-885f-4d89-83f5-99f07198f3de.png">

## Part 2: Remotely Connecting

1. To get remotely connected to server, begin by opening a new terminal 
in VSCode, by going to the top left of your screen (for Mac) and 
clicking on **Terminal** -> **New Terminal** or pressing Ctrl + '.

<img width="500" alt="Screenshot 2023-01-12 at 2 14 27 PM" src="https://user-images.githubusercontent.com/122497165/212192565-59d28023-64a0-4ce4-85e4-f9d2527d9de5.png">

2. Once the terminal is open, use 'ssh' in the command and insert your 'Course-SpecificAccountName@ieng6.ucsd.edu (e.g. 'ssh cs15lwi23abc'). Once you press enter, you 
will be prompted with a message asking 'Are you sure you want to continue connecting (yes/no/[fingerprint])? as it may be your first time connecting to a new server.

3. Input yes, and you will then input your password for your course-specific account (if it shows nothing being typed, you are currently inputting characters) and press enter, where you will then be prompted that you're logged into a computer (server) in the CSE basement!

<img width="500" alt="Screenshot 2023-01-12 at 2 36 02 PM" src="https://user-images.githubusercontent.com/122497165/212196046-300d1f67-b9ac-4cd2-bc59-1ff1249735a3.png">

## Part 3: Running Commands 

1. Now that you're remotely connected to a server, you may try running some commands 
like 'cd', 'ls', 'pwd', 'mkdir', and 'cp' in the terminal.

2. A command like 'pwd', will print the current working directory the terminal is using ('/home/linux/ieng6/cs15lwi23/cs15lwi23anf'). Inputting 'mkdir' followed by a new name will create a new directory in the current location with that name and using 'ls' will display the accessible contents of the directory (highlighted in blue).

<img width="500" alt="Screenshot 2023-01-12 at 2 44 02 PM" src="https://user-images.githubusercontent.com/122497165/212197159-bcbed63a-6b0c-4b9a-9231-83f3f7f31380.png">

3. After going through many of the commands, you can log out of the remote server in your terminal 
by using: 

* Ctrl-D
* The command 'exit'

**You have successfully setup your enviornment, remotely connect to a server, and run commands for CSE 15L!**
