###Example 1

**These excercises will cover the basic GDB commands.**

[Ex1](ex1.cpp) is a rough implementation of the `strcpy` function. It takes
two arguments, and the program copies the second argument onto the first.
Compile the file with the `-g` flag mentioned in the parent README.

If you pass in the arguments `hello` then `goodbye`, the output should be the following:

```
First: hello
Second: goodbye

COPY DONE

First: 
Second: Goodbye
```

Clearly, the copy function is flawed. At first, we might want to make print
statements in the function that output each character. Unfortunately, this
can result in long outputs. Also, it is tedious to go back and add print
statements at various locations. This is where GDB is useful.

Run GDB on the binary executable you compiled. You can run the program by 
typing `r` of `run` followed by the arguments you wish to pass in.

We can "step" through different parts of the program. Since we know the
error is occuring in the `my_strcpy` function, we can start there.

* Create a breakpoint where you think you should start looking.
  * Enter `b` or `break` followed by the line number where you want to place the break.
  If it was created you should see:
  `breakpoint 1 at 0x4007db: file ex1.cpp, line 19.`
  * Breakpoints are where the program "pauses". From here you can print different values.

From here, we want to explore what values the variables hold. For this, we use
the print command. 

* To print, type `p` or `print` followed by the variable/data structure you wish to observe.

Depending on where you are in the program, you can "step" through lines of code.
After entering a breakpoint, you can traverse the code that follows using `next`.
This is especially usefule because the program continues to execute every line you step
to. 

* To "step" through the program, enter `n` or `next`.

Here is a sample of how to use the `break`, `next`, and `print` commands.

```
 $ gdb a.out 

GNU gdb (GDB) Red Hat Enterprise Linux 7.6.1-47.el6
Copyright (C) 2013 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "x86_64-redhat-linux-gnu".
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>...
Reading symbols from /class/classes/cmanj001/cs100/GDB-Tutorial/a.out...done.
(gdb) b 22
Breakpoint 1 at 0x4008aa: file ex1/ex1.cpp, line 22.
(gdb) r hello goodbye
Starting program: /class/classes/cmanj001/cs100/GDB-Tutorial/a.out hello goodbye
First: hello
Second: goodbye

Breakpoint 1, my_strcpy (dst=0x7fffffffd1ec "hello", src=0x7fffffffd1f2 "goodbye") at
ex1/ex1.cpp:25
25      for(i = 0; src[i] != '\0'; ++i)
Missing separate debuginfos, use: debuginfo-install glibc-2.12-1.149.el6.x86_64
libgcc-4.4.7-11.el6.x86_64 libstdc++-4.4.7-11.el6.x86_64
(gdb) p src
$1 = 0x7fffffffd1f2 "goodbye"
(gdb) p dst
$2 = 0x7fffffffd1ec "hello"
(gdb) p target_size
$3 = 7
(gdb) continue
Continuing.

COPY DONE

First: 
Second: goodbye
[Inferior 1 (process 22293) exited normally]
(gdb) quit 
```

Using these commands, answer the following questions.

* What are the values of `src` and `dst` before and after the delete command?
* Is there a null pointer at the end of `dst` after the copy is complete?
