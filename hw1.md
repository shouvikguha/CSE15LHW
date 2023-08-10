
# Homework 1

Name: Shouvik Guha  
PID: A15990598  
Account: \<cs15lfa20aoz@ieng6.ucsd.edu\>  

## Getting Started

Login to your 15L account either from a lab machine or via `ssh`. From your
home directory, enter the following commands:

```
$ gethw hw1
$ cd ~/homework/hw1
$ vim hw1.md
```

Answer these questions in the `hw1.md` file you now have open.

___Don't forget to change the file header!___

1. Welcome to CSE 15L! You want to start your first homework assignment but don’t have a directory for all of your CSE 15L files. What command(s) can you use to create a new directory called `homework` under a directory called `cse15L` in your home directory. Assume you are currently in your home directory and that the `cse15L` directory does not exist yet. **(1 point)**

        mkdir cse15L
	cd cse15L
	mkdir homework

2. Assuming you are still in your home directory, what command can you use to move to your newly created `homework` directory. **(1 point)**

       	cd cse15L/homework

3. You are now ready to work on your first assignment! Assume you are in the `cse15L/homework` directory. What command can you use to create a file called `Assignment1.txt`? **(1 point)**

        touch Assignment1.txt

4. You realize that you would like your file to be a Markdown file instead of a text file so you can add plain-text formatting to your document. What command can you use to rename the file you just created to `Assignment1.md`? Assume you are currently in the `homework` directory you created in question 1. **(1 point)**

       mv Assignment1.txt Assignment1.md 

5. After renaming your file, you’re ready to start working but your dog comes and steps all over your keyboard! You want to make sure that your dog did not change directories in the process. What command can you use to check the path of your current directory? **(1 point)**

        pwd

6. You decide to use the Vim text editor to work on your homework assignment in the `Assignment1.md` file. As you write your name at the top of the file, you realize that your dog must have broken the shift and caps lock keys on your keyboard, as you are not able to capitalize any letters in your name. What vim command can you use to flip the case of a **single** letter (lower case to upper case and vice versa)? **(1 point)**

        If shift is not working and neither is caps lock, exit to visual and select the character(s) then copy paste a tilde symbol from google 

7. You realize that it might be easier to work on your assignment if you can see line numbers. What is a vim command you can use to enable line numbers when in command mode? **(1 point)**

        :set number

8. It would be a good idea for line numbers to show up by default whenever you open a new Vim file. What is the name of the file you can create in your home directory to save all your Vim settings? **(1 point)**

        .vimrc

9. You are almost done with your assignment but noticed that you skipped answering a question. If you are currently in command mode and your cursor is on line 20, what is the single vim command you can use to create an empty line on line 21 and enter insert mode? **(1 point)**

	o        

10. You accidentally deleted part of your answer to question 9! Give a single vim command to undo this mistake. **(1 point)**

        u or :u

11. After finishing the answer to the last question, you realized that your answer was incorrect. What vim command can you use to delete lines 20 - 25 (inclusive) of the file if your cursor is on line 20? **(1 point)**

        either 5dd or :20,25d

12. As you review your assignment, you notice that you skipped writing your CSE 15L username on line 3. What is a valid vim command (in command or normal mode) to jump to line 3 so you can add your username? **(1 point)**

        :3

    1. `echo` (Unix command) **(1 point)**

            Display line of text

    2. `man` (Unix command) **(1 point)**

	    Helps to get information of command by passing it with man (short for manual)           

    3.  `ls` (Unix command) **(1 point)**

            List directory contents

## Turnin Procedure:
Be sure your `hw1.md` file is saved on your 15L account in the directory
`~/homework/hw1`. When logged into your 15L account, enter the following
commands:
```
$ cd ~/homework/hw1
$ turnin15L
```
Follow the Autograder prompts, using your UC San Diego email login credentials,
and you should be good to go! Make sure you get the confirmation email from
Autograder. Additionally, you can log in to Autograder to verify your submission.

# Homework 1
