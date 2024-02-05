
# Homework 4

Name: Shouvik Guha



## Getting Started

Login to your 15L account either from a lab machine or via `ssh`. From your
home directory, enter the following commands:

```
$ gethw
$ cd ~/homework/hw4
$ vim hw4.md
```

Answer these questions in the `hw4.md` file you now have open.

_Don't forget to change the file header!_

1. What command from Lab 4 helped us return to `factorial.main` from 
`factorial.fact` while debugging? **(1 point)**

        main[1] pop 
	main[1] where


2. From Lab 4, explain the purpose of our `CLASSES` variable for 
our Makefile. **(1 point)**

        It makes referencing the 3 files in Lab 4 much easier, and thereby making the test process easier. 

3. From Lab 4, what happens if we type the command `make test` after 
no changes were made to the dependencies? **(1 point)**

        A recompilation of the file is not needed, and will not be done. 
	
		*** No rule to make target `test'.  Stop.


4. You are a renowned software developer and you have been hired by an old
British boyband that wants to make a comeback in the industry. They ask you to
make an app to showcase their new music and events. In your implementation, you
have a class for each of the 5 group members, but you find that compiling each  
band member’s class takes more time than you currently have. Luckily, you  
remember that you learned about Makefiles in your favorite online class! You
decide to create a Makefile to compile your classes to make testing more
efficient. Since Makefiles can have multiple rules, write out the general
structure of a single rule and explain how it should be interpreted.
**(1 point)**

        target: dependency1 dependency2 
		command1 
		command2
		command3

- Dependencies can name other targets in Makefile
- If any dependency is old, make will remake it
- Thereby creating chain of dependency

When you are attempting to make target, the makefile will make sure that the date the target is made is going to be the oldest date a dependency file can be modified. If the target is older than any of the dependencies, it will be recreated using commands, so that the date problem is fixed. The targets will then be written in as commands. Make interprets a makefile rule. Each rule comes with a target (which refers to a filename or action). 

5. The lead singer, Zayn Malik, wants to see his name printed every time his
rule is run. Write out the action that will print the phrase `Zayn Malik` to the
terminal. **(1 point)**

	vim Makefile
	Zayn: Z
		echo "Zayn Malik"
	Z: 
		Touch Zayn

:wq 
Make or make Zayn should then print "Zayn Malik"


6. Zayn Malik insists that his rule is run by default whenever `make` is called.  
When you run `make` with no arguments, which rule is used by default?
**(1 points)**

        When running make with no arguments, the first rule is used by default. 


7. Your Makefile contains a rule named `rockon`. What line do you need to add to
your Makefile to ensure it is run every time `make rockon` is called, even if
`rockon` is a file that exists in the current directory? **(1 points)**

                .PHONY: rockon

8. To help keep up with the endless demands, you create the following structure.
Explain what the following lines do in a Makefile:  **(1 point)**

    ```Makefile
    .SUFFIXES: .java .class
    .java.class:
        javac $<
    ```

    The first two lines help tell us the relation between java and class, i.e., in order to make a .class file, this will run javac on the .java file in question. After which, javac $< refers to the first dependency in the makefile (in this case that being .java of .SUFFIXES)



9. Makefile Practice: Tired with the old boys, you settle down to relive simpler
times, but make some errors in your Makefile. Can you fix them? See Makefile for
details **(5 points)**

## Turnin Procedure:
Be sure your `hw4.md` file is saved on your 15L  account in the directory
`~/homework/hw4`. When logged into your 15L account, enter the following
commands:
```
$ cd ~/homework/hw4
$ turnin15L
```
Follow the Autograder prompts, using your UC San Diego email login credentials,
and you should be good to go! Make sure you get the confirmation email from
Autograder. Additionally, you can log in to Autograder to verify your submission.

## Studying?
While the answers aren't posted on this page, you can access old questions on
<a target="_blank" href=https://autograder.ucsd.edu>Autograder</a>! Log in and
find your graded assignments. When you open a graded assignment, you can see
the criteria we graded with. Good luck!
