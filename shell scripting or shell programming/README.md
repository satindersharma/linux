# Shell Scripting/Shell Programming

Shell is resposnible to read command / provided by end user. Shell will check wheter command is valid or not or whether properly used or not.
If it is valid and properly used, then shell interprets (converts) that command into kernal understanble form. That interpreted command will be handovered to kernal.
Kernal is responsible to execute that command with the help of hardware.

Shell acts as interface between user and kernal.
Shell + Kernal is nothing but operation system.

Types of shells:
--

There are multiple types of shell are available.

1.Bourne shell:
--
It is developed by stephen Bourne.
This is the first shell which is developed for unix.
By using sh command we can access this shell.

2.BASH Shell:
--
BASH      ->    Bourne Again SHell
It is the advanced version of Bourne shell
This is the default shell for most fo linux flavours.
By using bash or bsh command, we can  access this shell.

3.Korn Shell:
--
It is developed by david Korn.
Mostly this shell community used in IBM AIX operating system
By using ksh command, we can access this shell.

4.Cshell:
--
Cshell developed by Bill Joy
c meant for california university
It is also by default available with unix
By using csh command, we can access this shell

5.Tshell:
--
T means terminal
It is the advance version as c shell
It is most commonly used shell in HP unix
By using tsh command, we can access this shell.

6.Zshell:
---
developedby Paul.
By using zsh command, we can access this shell

There are multiple shell are there

Note:
--
The most commanly used shell in Linux environment is BASH. It is more powerful than remaing shells.

How to check default shell in our system:
--

$ echo $0         ->      bash
$ echo $SHELL     ->      /bin/bash

we can also check the default shell information inside /etc/passwd file

$ cat /etc/passwd
durfa:x:1000:1000:durga,,:/home/durga:/bin/bash

How to check all avialble shell in our system
--


