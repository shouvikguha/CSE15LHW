# Homework 2

Name: Shouvik Guha  

## Getting Started

Login to your 15L account either from a lab machine or via `ssh`. From your
home directory, enter the following commands:

```
$ gethw
$ cd ~/homework/hw2
$ vim hw2.md
```

Answer these questions in the `hw2.md` file you now have open.

_Don't forget to change the file header!_

1. Please take a look at the code in `hw2.c`. You may use this code to
answer questions 2 through 7. (_hint:_ you can compile this code by typing
`gcc -std=c99 -o hw2 -g hw2.c`, and you can run it by typing `./hw2`. For this
question, let's assume you're taking CSE 12 and the PA is due in 25 minutes.
Yikes! When you run your program with the command: `./hw2`, the output is not
what you expect. Instead, it seems like `is_prime` always returns false! You can
try this on your own!

    1. Which file descriptor is `expected: true` sent to? **(0.5 points)**

            Output is sent to FD 2 (standard error) referring to number 9697 
(fprintf mentions that it is stderr for the particular part that prints expected:true)

    2. Which file descriptor is `output: false` sent to? **(0.5 points)**

            Output is sent to FD1 (standard output) referring to number 9697 as seen below 

$ command 1 > output: number 9697 is prime -> false

2. What is the command to debug `hw2.c` using GDB, assuming that the
corresponding executable is named `hw2`? Assume your current directory includes
the executable. **(1 point)**

        gdb hw2


3. You want to set a breakpoint in the function `main`.

    1. What is one way to set a breakpoint in `main`? **(0.5 points)**

            (gdb) break main
	    (gdb) run

    2. What is another way to set a breakpoint, different from the solution you
    provided in part 1? (_hint:_ Remember that shorthands such as `bt` for 
    `backtrace` are not considered different) **(0.5 points)**

            Either (gdb) b 17 (the line where main has started) or (gdb) b main 

4. At some point during debugging, you see the following being printed *after*
you typed in "next": `22 input = 9697;`. What will be printed if you enter
`print input`? **(1 point)**

        (gdb) next
	22	    input = 9697;
	(gdb) print input
	$1 = 0


5. Following question 4, which is the next line to execute if you enter `next`? 
**(1 point)**

 	22 input = 9697;

       <!-- (gdb) next -->
       <!--	23	    output = is_prime(input); -->
       <!--	(gdb) print input -->
       <!-- $2 = 9697 -->


6. Say you are on this line: `23 output = is_prime(input);`. What is a command
in GDB that will bring your debugging INTO the function `is_prime()`? (_hint:_
this is different than staying within the `main` method) **(1 point)**

	(gdb) s

       <!-- (gdb) b is_prime -->
	

7. Let's say we want to see the value of output after `is_prime()` is finished. 
We can first enter the following command, `break 32` in GDB. From the previous 
problem, what is one command that will run the program until the new breakpoint
that we just created? **(1 point)**

        First we make sure we run using (gdb) run after which, use (gdb) c to continue to next breakpoint(s)

8. Now quit GDB. Let's say you've fixed the bug in your code. Nice! Now you
want to save the output printed by your program in order to compare with a
reference solution. What is a command to use in order to redirect *only* the
standard output of `./hw2` to a file named `my_sol`? **(1 point)**

        ./hw2 >> my_sol or ./hw2 > my_sol (if appending not req)

9. Assume that you have a reference solution file named `ref_sol` that
contains the expected output of this PA. What is the command to help you check
whether `my_sol` and `ref_sol` have any differences? **(1 point)**

        diff my_sol ref_sol

10. Your solution looks perfect. Good job! Now, you are worried if your program
has any memory violations, so there are yet more things to check. Using the program described in lecture, what is the complete command that can help you check for any potential memory issues, like memory leaks or invalid memory accesses in your hw2 executable? (hint: it is not simply make valgrind!) (1 point)

	make valgrind
	valgrind --leak-check=full ./hw2

11. You have a file called RickTutor.txt that contains over 10,000 lines listing the names and instructors of all CSE courses offered every quarter from 2002. However, you’re only interested in lines that contain the course name CSE15L. For the following questions, try making a small tester file to make sure your commands work correctly.

	1. What is the command that displays all lines containing the phrase CSE15L with their corresponding line numbers in RickTutor.txt and outputs them to a file with the name GaryTutor.txt? (0.5 points)

		grep -n CSE15L RickTutor.txt > GaryTutor.txt

	2. We want to count the number of lines that contain the phrase CSE15L. What is the command? Do NOT send the output to a file for this command. Hint: Check out man grep for available options!

		grep -c "CSE15L" GaryTutor.txt



