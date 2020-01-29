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
| &darr; | &#8739; |
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
13. exit  ---> to exit the terminal or to logout session

Type of files:
----

In Linux everything is treated as file.
All files are devided into 3 types.
1. Normal or Ordinary files.
2. Directory files.
3. Device files.

Normal or Ordinary files:
---------
These files contain data. It can be either text file like abc.txt or binary file like images, videos, audios etc.

Directory files:
---
These files represents directories. In windows we can use folder terminology whereas in Linux we can use directory terminology.
Directory can contain files and sub directories.

Device files:
----
In Linux every device is represented as a file. By using we can communicate with that device.
/dev/pts/0    ---> file representing first terminal
/dev/pts/1    ---> file representing second terminal
$ echo "Hello"              --->  Hello will be printed to terminal
$ echo "Hello" > abc.txt    --->  Hello will be written to abc.txt file
$ echo "Hello" > /dev/pts/1 --->  Hello will be displayed on the second terminal


How to check file type?
------
<pre>
Blue color represent directoriies and all the remaining are files.
But this color convertion is varied from flavour to flavour, hence this approach can't be used to check file type we should use 'ls -l' command.
We should use ls command with -l option
$ ls -l
-rwxr-xr-r 1 durga durga 43 jan 5 16:07 demo.sh
drwr-xr-r  2 durga durga 4094

The first charcter repersent file type:
- normal file
d directory file
l linked file
c character special file
b block specific file
s socket file
Note: c,b,s representing system file and mostly used by super user.
</pre>

File System Navigation Commands:
--------
<pre>
Every directory implicity contain two hidden files   .  and   ..
.   represents currunt working directory
..  represents parent directory
~   represents user home directory ( /home/durga/ )
-   represents previous working dirctory
/   represents root directory
</pre>
eg    Assume we are in /home/durga/Desktop/dir1/dir2
<pre>
$ cd /
pwd: /

$ cd .
pwd: /home/durga/Desktop/dir1/dir2

$ cd ..
pwd: /home/durga/Desktop/dir1

$ cd ../../..
pwd: /home/durga

$ cd ~
pwd: /home/durga

$ cd -
pwd: change to previous working directory
</pre>
Note: If we are not passing any argument to cd command then we will move to user home directory

Linux File System:
----


linux file system has tree like structure.
It starts with root (/).
/ is the top most directory.
The root directory contains the following important sub-directory. bin, sbin. lib, etc, home, var, usr etc.

1.bin directory:
-----------


bin means binary.
whenever we are using any command, internally some application will work to perform required activity. These command related application which are used by user will be stored inside bin directory i.e bin directory contains all binary excecutable related to our linux commands.
$ which ls
/bin/ls     -->   ls is available inside bin.

2.sbin directory:
----


sbin means secondary bin/system bin.
It contains all binary executable related to high end admin used command.
eg: disk partitioning, network managment etc.

Q. What is the difference between bin and sbin?
---


bin contains binary executable related to command used by normal user.
sbin contains binary ececutable related to command used by super user.

3.etc directory:
---


This directory contains all system configuration files.
These configuration can be used to customised behavour of linux operating system.
The users information is available in /etc/passwd file.
The group information is available in /etc/group file.
Host information (like ip address and dns name) is available in the /etc/hosts file.

4.tmp directory:
---


tmp means temp directory. If any file required temprarily, such type of files are temprary fils are recommended to create tmp directory.
These files will be deleted automatically at the time of system shutdown so that memory utilization will be improved.
If any file which is required permantaly not recommended to create inside tmp directory.

5.dev directory:
---


dev means device.
In Linux everything is treated as file, even devices also. Every device is represented as a file. by using that file we can communicate with that device. All device related file will be stored inside dev directory.
eg.
tty     ->  terminal related file.  
hd      ->  floppy disk related file.   
fd      ->  hard disk related file.  
ram     ->  ram related file.  
stdin   ->  standard input device related file.  
stdout  ->  standard output related file.  
stderr  ->  standard error related file.  

6.mnt directory:
---


mnt means mounting.
we have to attach external file system files from pendrive, cd external drive etc to linux file system then only we can use these external file.
This attachment proccess is called mounting.
In the older operating system we have to perform mounting manually but in recent operating system mounting willl perform automatically and we are not required to perform manually. The files of manual mounting will be palced inside mnt directory.

7.media directory:
---


The files which are available because of automatic mounting will be placed inside.

Q. What are the difference between mnt and media directories?
---

mnt   ->    contains manual mounting file.
media ->    contains automatic mouting file.

8.opt directory:
--
opt means optional
This directory contains all third party software installation files.
eg. If we are installing any software explicity like google chrome,then the corresponding installation files will be stored inside opt directory.

9.lib directory:
----

lib means library.
It contains linux os libraries which are required by commands and applications.

10.var directory:
---
var means variable data
If any data which is keep on changing such type of data will be stored inside var directory.
eg..   files will be stored inside var.

11.home directory:
---
As linux is multiuser operating system, for every user a seprate directory will be created to hold his specific data like videos files, image, documents etc. This directory is called user home directory. All these user home directory will be related inside home directory.

12.root directory:
--
<pre>
It is the home directory or super user(root user)
/home/durga   ->    durga user home directory
/home/ravi    ->    ravi user home directory
/root         ->    super user home directory

Note:   / and root are different. root is the child directory of /
</pre>
13.proc directory:
--
proc means process
In linux multiple processes are running symntanously, for every proccess a unique id will be there which is also known as PID.
The data related to currunt running proccess will be stored inside proc directory.
For everyy proccess a seprate directory will be created inside prox to maintain that data. The name of this directory is same as PID.

14.boot directory:
--
boot means booting.
This directory contains the file which are required to boot operating system.

15.usr directory:
--
usr means user
This directory contain all user softwares.
1. The main advantage of file system is operating system can locate required files very eaisly.
2. ext2, ext3, ext4, XFS are names of linux file system.
NTFS, FAT names of windows file system.

Linux Installation.
