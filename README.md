Overview of UNIX/LINUX Operating System
---------------------------------------

What is UNIX?
It is a operating system by using that user/Application can communicate with hardware components.
It was developed in 1960's.
with the lots of extentions to the base version.
several flavours introduced by organisation/companies (flavours like Linux, ubuntu, centos etc).

Features of UNIX:
-----------------
1. It is FOSS (Freeware and Open Source Software).
2. UNIX can be used by multiple users simultaneously and hence it is multiuser operating system.
3. Several tasks can be executed simultaneously and hence it is multitasking operationg system.
4. It is user friendly and provides support for both CUI and GUI.
5. When compared with window UNIX is more secured.


Flavour of UNIX:
----------------
As UNIX is open source, multiple flavour are available with lots of extensions and improvements.

1. UNIX
2. Red Hat
3. Centos
4. Fedora
5. Stackwave
6. open salories
7. Suse Linux Entersprise Server (SLES)
8. open Suse
etc

All these flavours have lots of similarities. Hence if you are prefect with one flavour, we can work on any flavour very eaisly.

Note:  We can see a detailed list of Linux flavour in www.distrowatch.com 

Components of UNIX:
------------------

User

&nbsp;&nbsp;&darr;

Application

&nbsp;&nbsp;&darr;

Shell

&nbsp;&nbsp;&darr;

Kernal

&nbsp;&nbsp;&darr;

Hardware

----

Shell:
-----
It is the outer layer of UNIX OS.
It reads our command verify whether it is valid or not and whether it is properly used or not. If everthing is proper the shell convert/interpretes the command into kernal understandable form and have over the kernal.
Shell acts as interface bitween user and kernal.

Kernal:
----
It is the core component of UNIX OS.
It is reponsible to execute our command.
It is reponsible for memory allocation and time allocation.
Kernal acts or interface bitween shell and hardware

Note:
Shell and kernal together considered as operating system.

Command Exicution Flow:
-----

|         |            |
| :-----------: |:-------------:|
| End User types a command on the terminal eg. touch sunny.txt| |
| &darr; | |
| command will be submitted to the shell      |      |
| &darr; | |
| shell checks whether this command is valid or not and whether it is properly used or not| If it is not proper display error message to the terminal|
| &darr; | |
| kernal exicute that command and perform required action | &#8739; |
| &darr; | &#8739; |
| Again $ promt will be displayed to the teminal which indicates ready for the next command | &#8626; |


Note: In Linux there are two types of users, Normal User and Super User. Super User also known as Root User or Admin.

$ promt for Normal User
<p># promt for Root User

Shortcut to open Terminal    Alt+Ctrl+T
Shortcut to close Terminal   Ctrl+D

Online UNIX Terminal:
------
www.masswork.at/jsuix
It is free terminal and written completly in javascript.
We can access in any browser.
We can use this terminal only for test basic command.

Very Basic Command Overview:
----
1. pwd    ---> print working directory, present working directory
2. ls     ---> to list out all files and directories
3. mkdir  ---> to create a directories
4. cd     ---> change directory
5. touch  ---> to creation empty file
6. rmdir  ---> to remove a directory
7. rm     ---> to remove a file
8. cal    ---> to display current month calender
9. date   ---> to dispaly currunt system data and time
10. help  ---> to listout all available command
11. hello ---> to display brief system information
12. clear ---> to clear the terminal
