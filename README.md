===

#Introduction to GDB

Root Location: https://github.com/ManjunathChet/GDB-Tutorial.git

*Contributors:*

*Chetas Manjunath*

*Bridget Bennecke*

License: GNU GENERAL PUBLIC LICENSE
*--Refer to LICENSE file--*

---

**Description**

GDB is a debugger that allows the user to observe what is happening in a specific 
program. The purpose of this tutorial is to familiarize users with the basic
GDB commands and their uses.

**Setup**

GDB is a tool that controls how a program runs. If the user wants to give GDB
access to the program, the user has to compile the files using a specific flag.

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

The GDB prompt should look like the following:

```
GNU gdb (GDB) Red Hat Enterprise Linux 7.6.1-47.el6
Copyright (C) 2013 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "x86_64-redhat-linux-gnu".
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Reading symbols from <your program location>
```

**Runtime**

GDBs UI is similar to bash. Users enter certain commands and arguments into the
prompt. The commands that will be covered are the following:

`r` or `run`

`p` or `print`

`b` or `break`

`n` or `next`

`c` or `continue`
