
# Homework 5

Name: Shouvik Guha



## Getting Started

Login to your 15L account either from a lab machine or via `ssh`. From your
home directory, enter the following commands:

```
$ gethw
$ cd ~/homework/hw5
$ vim hw5.md
```

Answer these questions in the `hw5.md` file you now have open.

_Don't forget to change the file header!_

1. In Lab5, why did we set aliases in our .bashrc file?

        We use aliases to help call long and frequently used commands, faster. By editing them into a .bashrc file, these commands are automatically loaded every time one logs in. 


2. From Lab5, what command do you need to run after making changes to your .bashrc file to ensure the changes take effect?

        source ~/.bashrc


3. You've been working odd hours and weekends on your pet project, Pet Rock
Simulator, and it is almost complete. You make some final polishes, crack your
knuckles, and get ready for the inaugural playthrough. The first time you start
your program, though, BAD NEWS!! Unhandled Exception. You look through the stack
trace:


        Exception in thread "AWT-EventQueue-0" java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 4
	        at petrockco.PetRock.setEmotion(PetRock.java:320)
	        at petrockco.SimEnv.updateEmotion(SimEnv.java:114)
	        at petrockco.PetRockSimulator.onButtonPress(PetRockSimulator.java:62)
	        at java.desktop/java.awt.Button.processActionEvent(Button.java:411)
	        at java.desktop/java.awt.Button.processEvent(Button.java:379)
	        at java.desktop/java.awt.Component.dispatchEventImpl(Component.java:5011)
	        at java.desktop/java.awt.Component.dispatchEvent(Component.java:4843)
	        at java.desktop/java.awt.EventQueue.dispatchEventImpl(EventQueue.java:772)
	        at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:721)
	        at java.base/java.security.AccessController.doPrivileged(Native Method)
	        at java.desktop/java.awt.EventQueue$5.run(EventQueue.java:745)
	        at java.base/java.security.AccessController.doPrivileged(Native Method)
	        at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:85)
	        at java.desktop/java.awt.EventQueue.dispatchEvent(EventQueue.java:742)
	        at java.desktop/java.awt.EventDispatchThread.pumpOneEventForFilters(EventDispatchThread.java:203)
	        at java.desktop/java.awt.EventDispatchThread.pumpEventsForFilter(EventDispatchThread.java:124)
	        at java.desktop/java.awt.EventDispatchThread.pumpEventsForHierarchy(EventDispatchThread.java:113)
	        at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:109)
	        at java.desktop/java.awt.EventDispatchThread.run(EventDispatchThread.java:90)


4. Looking at the stack trace above, what was the unhandled exception? **(1 point)**

        ArrayIndexOutOfBoundsException


5. Looking at the stack trace above, what file and line generated the unhandled exception? **(1 point)**

        at petrockco.PetRock.setEmotion(PetRock.java:320
)
6. You decide to put your new JDB skills to use and track down the issue. Once
your program is loaded into JDB, what command can you use to set a breakpoint at
line 114 in file SimEnv.java? **(1 point)**

        > stop at SimEnv:114 or > stop at SimEnv.java:114


7. Your program ran and stopped at the breakpoint. You have no idea what is
wrong at this point, but you wonder if a value is set incorrectly. What is the
command to list all variables in the local stack frame? **(1 point)**

        info locals (gdb) or locals (jdb)

8. Aha! The emotional index variable is off by one for your pet rock, Dwayne
Johnson.  It must have been set incorrectly previously in your code. With your
code currently paused, what command can you use to go up one level in the stack?
**(1 point)**

        pop

9. Success! Your program is running like a charm. Now that you have your alpha
version, you want to stress test the game by letting it run for several days.
Since you don't want to sit and watch it, you decide to create a script to
monitor your process list to make sure the program is still running. Using `ps`
and `grep`, write a single command with pipe to search through all processes on
your machine for a process with the name `PetRockSimulator` and print it to the
terminal if it is found. (HINT: Look at `man` pages of `ps` and `grep`)
**(1 point)**

        ps -ef | grep PetRockSimulator

10. Since `grep` outputs an exit status code, you can use it in place of the
test-command in your `if` statement. Excellent! You also put in error logging
into your code, which will output any errors to standard error. If you run your
program using `java PetRockSimulator`, write the full command you would run to
redirect all standard error from your program to a file called `errorlog.log`.
**(1 point)**

        java PetRockSimulator 2 > errorlog.log

11. After weeks of successful trials, you release your program to the class for
all to enjoy. You want to track how popular it is, so you write a script to
record a running sum of the number of users running the program each day at
noon. You record the value in your script in a variable called `sumusers` and
the number of users using PetRockSimulator today as `numtoday`. Write two
different methods of adding `sumusers` and `numtoday` and saving the result in
`sumusers` using `expr` and `$((...))` notation. **(2 points)**

        sumusers = "expr $sumusers + $numtoday"
	numtoday = "sumusers - expr $sumusers"
	sumusers = "expr $sumusers"


## Turnin Procedure:
Be sure your `hw5.md` file is saved on your 15L  account in the directory
`~/homework/hw5`. When logged into your 15L account, enter the following
commands:
```
$ cd ~/homework/hw5
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
