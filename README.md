===

#Introduction to GDB
Root Location: https://github.com/ManjunathChet/GDB-Tutorial.git

---

**Description**

GDB is a debugger that allows you to observe what is happening in a specific 
program. The purpose of this tutorial is to familiarize you with the basic
GDB commands and their uses.

**Setup**

GDB is a tool that controls how a program runs. If you want to give GDB
access to the program, you need to compile the files using a specific flag.

Before we begin, we need to give GDB access to our program. In order to do this,
simply add the `-g` flag to the compile command.

For example, if your compile flags are:

` -W -Wall -Werror -ansi -pedantic`
 
a GDB compatible counterpart would be:

`-W -Wall -Werror -ansi -pedantic -g`

Next, you will need to run GDB on the specific program you compiled. In bash,
type `gdb` followed by the program you wish to debug. 
For example: `gdb ./a.out`

_Dont worry about passing arguments into your program, this will be covered in 
later with the run command (`r`)._

**Runtime**

GDBs UI is similar to bash. Users enter certain commands and arguments into the
prompt. After you start GDB, you can configure how the program will run with these
commands. To understand how this works, lets look at the following examples.

[Example 1](ex1/)

**Example 2**

_This is where another print and continue tutorial will go. It will consist of
observing different elements of a struct._

**Example 3**
_Stepping though a segmentation fault to find where the error is._


