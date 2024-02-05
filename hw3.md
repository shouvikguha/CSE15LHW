# Homework 3

Name: Shouvik Guha 

## Getting Started

Login to your 15L account either from a lab machine or via `ssh`. From your
home directory, enter the following commands:

```
$ gethw
$ cd ~/homework/hw3
$ vim hw3.md
```

Answer these questions in the `hw3.md` file you now have open.

_Don't forget to change the file header!_

1. You are about to sell your personal laptop because you saved up enough money for an upgrade! However, you don't want to lose all the hard work you did for CSE 15L (your favorite class!). To save your work, you decide to copy your work on the `ieng6.ucsd.edu` server. What command can you use to copy the `~/Documents/School/CSE15L` folder on your current laptop to your home directory in your remote CSE 15L account? Assume your CSE 15L username `cs15lfa20sny`. **(1 point)**

        cd 
	scp -r ~/Document/School/CSE15L cs15lfa20sny@ieng6.ucsd.edu:~


2. After buying a new laptop, you want to access your CSE15L account to continue editing your files. What command can you use to log in to the remote `ieng6.ucsd.edu` server? Assume your username is the same as in the last question. **(1 point)**

        ssh cs15lfa20sny@ieng6.ucsd.edu


3. However, when you first saved all your homework for CSE 15L, you didn't organize everything well, so your files aren't easily accessible. Luckily, you still remember that the file you want to find is located in a subdirectory of `~/CSE15L` and that its name includes `hw3`. What is the command you can use to find a path to your homework? **(1 point)**

        cd ~/CSE15L
	find . -iname "hw3*"


4. Using the command from question 3, you found that the path of the file you want is `~/CSE15L/Week3/Homework/hw3.md`. From your home directory, what **single** command allows you to scroll through the content of a file **without opening it in an editor or touching your mouse/touchpad**? **(1 point)**

        
	more ~/CSE15L/Week3/Homework/hw3.md
	OR
	less ~/CSE15L/Week3/Homework/hw3.md 
	<!-- cat ~/homework/hw3/hw3.md -->


5. You want to write a bash script to automate testing one of your scripting projects. At the top of the newly created file `test.sh`, what line should you put to indicate to the OS that the following commands should be invoked in a bash shell. **(1 point)**

       #!/bin/bash


6. When you try to execute the script that you just wrote with `./test.sh`, your terminal says `Permission denied`, so you wonder what are the exact permissions of your script. You know your script is located in your current working directory. What is the command to use to check the permissions of **ALL** your files in your current directory? **(1 point)**

        ls -l   

7. After executing the command in the previous question, you find that the permissions of the script are `-rw-r--r--`. What command can you use so that you (the owner) can execute the file test.sh while keeping the permissions for group and others the same? **(1 point)**

        chmod u+x test.sh


8. After changing the permissions and running your script, you realized that your project doesn't work as expected. You opened up your favorite IDE, IntelliJ, and ran the program with the debugger. After the program finishes its execution, what is the name of the panel on which should you be able to find your stack traces?  **(1 point)**

        "Frames"

9. After working on your homework and running your tests, you want to make sure no further edits are made to files in your `~/CSE15L` directory. What command can you use to remove write and execute permissions for all users for all the files in `~/CSE15L`. Assume you are currently in the home directory. **(1 point)** **(1 point)**

	chmod a-wx ~/CSE15L/*
	OR
	chmod ugo-wx ~/CSE15L/*

## Turnin Procedure:
Be sure your `hw3.md` file is saved on your 15L account in the directory
`~/homework/hw3`. When logged into your 15L account, enter the following
commands:
```
$ cd ~/homework/hw3
$ turnin15L
```
Follow the Autograder prompts, using your UC San Diego email login credentials,
and you should be good to go! Make sure you get the confirmation email from
Autograder. Additionally, you can log in to Autograder to verify your submission.

