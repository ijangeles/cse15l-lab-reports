# Lab Report 4
## Competition Tasks
This lab report will go over reproducing the tasks from the Week 7 Lab competition, using special keys and shortcuts that can speed up the process of going through the tasks through the use of the Bash History, the `tab` key, quick copy/paste, and many other keyboard shortcuts that can help edit commands. 

## Setup
**1. Deleting existing forks of the repository**

Before proceeding with the lab tasks, we need to delete any existing forks of the Lab 7 Repository on the account. We do this by deleting the fork of the repository on GitHub Desktop and going into the repository through Github and deleting the repository from the account.

Removing the fork from Github Desktop:

<img width="500" alt="Screen Shot 2023-02-23 at 1 01 47 PM" src="https://user-images.githubusercontent.com/122497165/221029356-94c3ad7c-06c1-4c17-9ab7-39550ab2ce39.png">

Going into the settings of the repository, scrolling down to the **Danger Zone** and deleting the repository:

<img width="500" alt="Screen Shot 2023-02-23 at 1 06 45 PM" src="https://user-images.githubusercontent.com/122497165/221030241-9bf0b5d5-3270-4837-b786-01a59fee4cab.png">

This step does not require any commands or keypresses as it's part of the setup before the real tasks. This setup step deletes the existing forks of the repository before beginning a new run through of the lab tasks within the repository. This is an important step as reproducing the tasks again on the existing fork, **after** it has been edited will prevent the user from making new changes, as the change was already made on the repository.

**2. Forking the repository**
After deleting existing forks of the repository, we must now do a new fork of the repository to setup before the real tasks. 

After forking the Lab 7 repository, we can now make a fresh clone of the repository on Github Desktop:

<img width="500" alt="Screen Shot 2023-02-23 at 1 18 12 PM" src="https://user-images.githubusercontent.com/122497165/221032399-e182b891-f879-41fb-bf66-c9835cf87fe2.png">

After this setup step, we will now be able to begin the timer for the real task, where we will start first with logging into a local computer with `ieng6`.

## The Tasks
After setting up the repository, we will now be reproducing the lab tasks on the repository, while utilizing the Bash History, the `tab` key, quick copy/paste, or other keyboard shortcuts

**3. Logging into ieng6**


*Keys pressed:* `<Ctrl-r>, "ssh", <enter>`

![Screen Shot 2023-02-23 at 1 35 51 PM](https://user-images.githubusercontent.com/122497165/221035768-261c0e67-b68d-46e2-92de-303f632318a3.png)

Rather than typing out the full `ssh cs15lwi23__@ieng6.ucsd.edu`, I used `<ctrl-r>` to access my bash history, using the reverse search to look for the command starting with `"ssh"`. After typing the first three letters of the command, bash finds the full `ssh cs15lwi23__@ieng6.ucsd.edu` command as it's been used in the past. I then press enter and log into ieng6.

**4. Cloning the fork from Github account**

*Keys pressed:* `Typed: "git clone", <ctrl-c>, <ctrl-v>, <enter>`

![Screen Shot 2023-02-23 at 1 43 12 PM](https://user-images.githubusercontent.com/122497165/221037027-38bcd070-fa8b-40cc-80ea-4e839c80084c.png)

To clone the fork from my Github account, I first typed the `git clone` command into the command-line then went into my Github account to find the repository's ssh key. Using the ssh key helped in authenticating to Github, and so I copied the key using `<ctrl-c>` then pasted it after the `git clone` command with `<ctrl-v>` then pressed `<enter>` to clone the fork.

**5. Running the tests**

*Keys pressed:* `ls, cd "la" <tab>, <enter> `

*Keys pressed to find/run tests: `<ctrl-r> "javac", <enter>, <ctrl-r> "java", <down>, <down>, <enter>`

![Screen Shot 2023-02-23 at 1 57 14 PM](https://user-images.githubusercontent.com/122497165/221039688-592dccf5-7c1a-421d-8c23-558ef0a7de45.png)

After cloning the fork, I `ls` to list all the directories and found that the lab 7 was successfully cloned. I then `cd` and typed `"la"` then used `<tab>` to autofill the lab 7 directory and pressed `<enter>`. 

After changing directory into the `lab7` directory, I used `<ctrl-r>` to search for the command in my bash history starting with `"javac"` and found the  
`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command, where I then pressed `<enter>` to compile all the files. To run the test file, I used `<ctrl-r>` again to search for the command using `"java"`, and the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` command was 2 down in the history so I accessed and ran it the same way when I compiled the files. In this step, I compiled all the files and then ran the `TestListExamples` tester file to demonstrate that the tests fail.

**6. Editing the code file to fix the test**

*Keys pressed:* `nano "Lis" <tab>, scroll down to line 42 OR <down> 42x, <right> 12x, <delete>, input "2"`

*Keys pressed to save:* `<ctrl-o><enter><ctrl-x>`

<img width="500" alt="Screen Shot 2023-02-23 at 3 51 29 PM" src="https://user-images.githubusercontent.com/122497165/221057678-b4f768f8-290d-4b40-a25e-cff20c0099ba.png">

To edit the file with the error, I first had to open the `ListExamples.java` by using `nano` then typing `"Lis"` and using `<tab>` to autofill the file name. I then scrolled down to line 42 (OR do <down> 42 times) and moved the cursor `<right>` 12 times to get to where the error was. I then `<delete>` to remove the error and replace it with the correct character, which was `"2"`. In this step, I opened the ListExamples.java file to find the error and edit the line that was causing the error.
  
To save the changes, I used `<ctrl-o>` to save the changes and pressed `<enter>` to apply the changes. Then I use `<ctrl-x>` to exit out the file.

**7. Running the tests to show that they succeed**

 *Keys pressed:* `<ctrl-r> "javac" <enter>, <ctrl-r> "java" <up><up><up><up><up><enter>`
  
<img width="500" alt="Screen Shot 2023-02-23 at 4 10 39 PM" src="https://user-images.githubusercontent.com/122497165/221059984-3014bfe2-5446-4db8-84e6-896526a7f681.png">

To run the tests again, I opened up my bash history to search for the command that compiles the files by searching with `"javac"`, which autofilled in the command and pressed `<enter>`. I then opened the bash history again to search for the command that runs the test file. I input `"java"`, but the command was 5 up in the search history, so I used the up arrwo to access it and pressed `<enter>` to run the tests.
  
**8. Commit and push the change to Github**

*Keys pressed:* `git add "Li" <tab><enter>, <ctrl-r> "git commit" <enter>, git push`
  
<img width="500" alt="Screen Shot 2023-02-23 at 4 22 57 PM" src="https://user-images.githubusercontent.com/122497165/221061487-097ec473-ef49-4358-91ca-2b19e69e2b91.png">

Once the tests passes, I have to use `git add` with the file that was changed, typing `"Li"` and autofilling `<tab>` to `ListExamples.java`, which I enter to add the change to the current directory. I then go through my bash history to search for `git commit` and the command autofills `git commit -m "Updated"` as I used this command during lab. I press `<enter>`and finally, type out `git push` and press `<enter>` to push the change to my Github account.  
