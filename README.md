Description

This is a simple implementation of a UNIX command line interpreter. The shell can interpret and execute command line arguments read from the standard input. the shell read lines from a file or terminal line which is then interpreted and executed if the command is valid

Information

Output

Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.
The only difference is when you print an error, the name of the program must be equivalent to your argv[0] (See below)

Example of error with sh:

$ echo "Ian" | /bin/sh
/bin/sh: 1: qwerty: not found
$ echo "Ian" | /bin/../bin/sh
/bin/../bin/sh: 1: qwerty: not found
$

Same error with our program hsh:

$ echo "kanneh" | ./hsh
./hsh: 1: qwerty: not found
$ echo "kanneh" | ./././hsh
./././hsh: 1: qwerty: not found
$

List of functions and system calls we used

- access (man 2 access)
- chdir (man 2 chdir)
- close (man 2 close)
- closedir (man 3 closedir)
- execve (man 2 execve)
- exit (man 3 exit)
- _exit (man 2 _exit)
- fflush (man 3 fflush)
- fork (man 2 fork)
- free (man 3 free)
- getcwd (man 3 getcwd)
- getline (man 3 getline)
- isatty (man 3 isatty)
- kill (man 2 kill)
- malloc (man 3 malloc)
- open (man 2 open)
- opendir (man 3 opendir)
- perror (man 3 perror)
- read (man 2 read)
- readdir (man 3 readdir)
- signal (man 2 signal)
- stat (__xstat) (man 2 stat)
- lstat (__lxstat) (man 2 lstat)
- fstat (__fxstat) (man 2 fstat)
- strtok (man 3 strtok)
- wait (man 2 wait)
- waitpid (man 2 waitpid)
- wait3 (man 2 wait3)
- wait4 (man 2 wait4)
- write (man 2 write)

How the Project is Compiled

We compile our shell using:

gcc -Wall -Werror -Wextra -pedantic *.c -o hsh

Testing

Our shell should work like this in interactive mode:

$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$

Also in non-interactive mode:

$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$

The Project's Implementation in Review

Submission requirements:

Write a beautiful code that passes the Betty checks
Write a UNIX command line interpreter.
Functionalities
Our Shell does the following:
Display a prompt and wait for the user to type a command, ending wih a new line.
The prompt is displayed again each time a command has been executed.
The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.
The command lines are made only of one word. No arguments will be passed to programs.
If an executable cannot be found, an error message is displayed to the user, and then display the prompt again.
We will handle errors, including the “end of file” condition (Ctrl+D)
Using the man_1_simple_shell page
Display the page
 man ./man_1_simple_shell
 
Contributors

Rasheedat Olufunke Yusuf (yrasheedat12@gmail.com)

Cheick Ahmed Touré ()
