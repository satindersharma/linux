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
---
You can se this step by step on this link:
https://www.wikihow.com/Install-Ubuntu-on-VirtualBox
(change the controller IDE to load ubuntu from your iso file is not included in in this link)

### Step 1. Oracle VirtualBox Installation
<pre>
To run Virtual Computer in our system without effects origal computer, We should use virtualbox. It can execute the capability of our existing computer of that we can downlaod virtualbox software from:
download VIrtualBox:
https://www.virtualbox.org/   ->    downlaods   ->    windows Hosts

download ubuntu:
https://ubuntu.com/   ->    Download    ->    under Ubuntu Desktop   ->   18.04 LTS
(here ubuntu decide there version name on release year.month format like 18.04 LTS is the virsion release in 2018 april)

change no of proccesser in setting  ->  system  ->  proccessor  -> change to 2
(The no. of proccessor for virtual machine is set to 1 as default , to change it to 2 we need the virtualization enabled in BIOS)

(change the controller IDE to load ubuntu from your iso file)
--
setting  ->  storage  ->  in controller IDE click on empty  -> on right click on optical drive cd icon    ->    click on choose a disk file and select your  downloaded ubuntu iso file
now we can click on start   -> at some point after this there is two option 1. try ubuntu 2. install ubuntu -> click on install ubuntu
you can choose to minimal installation for fast install
Installation type: keep selected Erase disk and install ubuntu
</pre>
Various Important Points:
--
<pre>
ctrl+alt+t    ->    open terminal
ctrl+d        ->    close terminal
ctrl+shift++  ->    increase font
ctrl+-        ->    decrease font

full screen:      devices ->  insert guest addition cd image  ->  run
to copy containts from linux to window and viceversa: devices ->  shared clipboard ->  bidirectional    and then restart ubuntu
to drag and drop files: devices ->  drag and drop ->  bidirectional     and restart ubuntu
</pre>

ls command
---
<pre>
we can use ls command to listout all files and directories prsent in the given directory.
Note: we can get manual documentation for any command by using man.
$ man command_name
It provides complete information for any command.

various options of ls command.
1.$ ls ->  It will display all files and directories present in the current working directory in alphabatical order.
2.$ ls -r ->  It will display all files directories in reverse of aphabetical form.
3.$ ls -l ->  It will be display all files adn directories in long listing form.
eg.   -rwr-r-- 1 durga durga 0 jan 31 11:49 a.txt
in above -(file type)rwr-r--(file permission) 1(no of links) durga(owner name) durga(group name) 0(file size in bytes) jan 31 11:49(the last modified time or creation time) a.txt(file name)

4.$ ls -t ->  To display all files based on last modified data type most recent is at top and old are at the bottom.
5.$ ls -rt  ->  To display all files based on reverse of last modified data and time. Old files at top and recent files are at bottom.
6.$ ls -a   ->  a means all . To display all files including hidden files. hence . and .. also will be displayed.
7.$ ls -A   ->  A means almost all. To display all files including hidden files excluding . and ..
8.$ ls -F   ->  To display all files by type.
      directory         ->  /
      executable file   ->  *
      link file         ->  @

9.$ ls -f   ->  To display all files including hidden files by disabling colors.
10.$ ls -i  ->  To display all files including i-node number.
                  i-node is the address of location, where file attributes are stored.
                  The following are various file attributes.
                  1) The size of the file       2) No of links of the file    3) owner name     4) group name
                  5) creation time        6) last modified time   7) last accessed time         etc

11.$ ls -R  ->  -R means Recursive. It will list all files and directories including sub directory contians also.
12.$ ls -s  ->  -s means size in blocks/
                  It willl list all files and the number of blocks size by that file. 1 block = 1024byte = 1kb
13.$ ls -h  ->  To display in human readable form.
</pre>
Note:
---
<pre>
We can use these options symntanously. where we are using multiple option together then orer is not important.
eg. All the following commands are equals and produced same result.
$ ls -l -t -r
$ ls -t -r -l
$ ls -r -l -t
$ ls -ltr
$ ls -lrt
</pre>

Note:
--
<pre>
If large no files are available then we have to use more or less command to view list page by page.
head or tail to view perticular no of lines
$ ls -l -/etc | more          ->    to view page by page in forward direction
$ ls -l -/etc | less          ->    to view page by page in forward and backword direction
$ ls -l -/etc | head -5       ->    to view top 5 file
$ ls -l -/etc | tail -5       ->    to view last 5 file
</pre>

Date command:
----
<pre>
we can use date command to display currunt date and time of system.
various options:
1.$ date +%D      =>    To display only date in the form of mm/dd/yy
2.$ date +%T      =>    To display only time in the form of hh:mm:ss
3.$ date +%m      =>    To display only month value
4.$ date +%d      =>    To display only year value
5.$ date +%y      =>    To display only year value in yy form
6.$ date +%Y      =>    To display only year value in yyyy form
7.$ date +%H      =>    To display only hour value in 24 hour format
8.$ date +%M      =>    To display only minute value
9.$ date +%S      =>    To display only second value
</pre>
1.Create an empty file where file names cotains current system date.
--
$ touch durga$(date +%d%m%Y).log
2.Create an empty file where file names cotains current system date.
--
$ touch durga$(date +%d%m%Y%H%M%S).log
Note: If the file name contains date and time, then that file is said to be timestamp file.

calender command:
---
<pre>

1. $ cal          ->    display curruent month calender
2. $ cal 2020     ->    to display complete 2020 year calender
3. $ cal 08 2020  ->    to display august month 2020 calender
4. $ cal 1        ->    to display 1st year calender
5. $ cal 9999     ->    to display 9999 year calender
6. $ cal 10000    ->    error (cal is define in the range of 1....9999 years only)
</pre>
Working with direcroties:
---
<pre>

1.creation of directories:
$ mkdir dir1 dir2       ->    to create multiple directories

$ mkdir dir1/dir2/dir3 -> this will create only dir3 only and only if there is dir1 and dir2 is already created.

$ mkdir -p dir6/dir7/dir8 -> now this will create all the directories if not there.
-p    ->    path of directory. all directories in the discription path will be created. first dir6 will created and in that dirctory dir7 will be created and within dir7 directory dir8 will be created.
</pre>
e.g create 5 directories named with dir1...dir5 in these directories create empty file named with a.txt...d.txt.
--

<pre>
$ mkdir dir{1..5}
$ touch dir{1..5}/{a..d}.txt
</pre>
how to remove directories:
--
<pre>
we have to use rmdir command.
$ rmdir dir1      ->    to remove empty dir1

Note: rmdir command will work for empty directories. If the directory is not empty then we will get error. we can't use rmdir to remove files. hence it is waste and useless command in linux os.
If the directory is not empty then we should use rm command to remove that directory. all internal files and directory present in the directory will be deleted. rm command can be used even to remove files also. hence rm command is recommended to use over rmdir command.
</pre>
whenver we are using rm command for directories. we should use -r or -R option. hence it is not case senstive.
--

<pre>
$ rm dir1   -> error (can't remove dir1: Is a directory)
$ rm -r dir1   or $ rm -R dir1
$ rm -ri dir4     (i means interactive option)
</pre>
while removing files and directories, if we want confirmatin then we have to use -i option.
--

<pre>
$ rm -ir dir1
rm: descend into directory 'dir1'? y
rm: remove regular empty file 'dir1/d.txt'? y
rm: remove regular empty file 'dir1/b.txt'? y
rm: remove regular empty file 'dir1/c.txt'? y
rm: remove regular empty file 'dir1/a.txt'? y
rm: remove directory 'dir1'? y
</pre>
-f    force removeal( it is opposite to interactive)
--


while removing files and directories if we don't want any error messages then we should use -f option. It is opposite to -i. It will ignore non existing directories information.
$ rm dir -if dir1 ->    even dir1 is not avialable we won't get any error message.

verbose output optioin(-v):
--


If we want to know the sequence of removal on the screen we should use -v option.

<pre>
$ rm -rv dir3
removed 'dir3/d.txt'
removed 'dir3/b.txt'
removed 'dir3/c.txt'
removed 'dir3/a.txt'
removed directory 'dir3'
</pre>

Note: in linux operating sytem, there is no way to reverse remove files and directories. Hence while removing files and directories  we have to take special care.
--
<pre>
The following is the most dangrous command, becaouse it will remove total linux file system.
$ rm -r /         (never run this even for test purpose, it will delete the whole system)
</pre>

Case Study:
--

create this directory stucture.

|          |          |         |          |         |         |     /    |          |         |         |   |   |
|:--------:|:--------:|:-------:|:--------:|:-------:|:-------:|:--------:|:--------:|:-------:|:-------:|:-:|:-:|
|          |          |         |          |         |         |  &darr;  |          |         |         |   |   |
|          |          |         |          |         |         |   home   |          |         |         |   |   |
|          |          |         |          |         |         |  &darr;  |          |         |         |   |   |
|          |          |         |          |         |         |   durga  |          |         |         |   |   |
|          |          |         |          |         |         |  &darr;  |          |         |         |   |   |
|          |          |         | &#11024; | &#8213; | &#8213; |  &#8213; |  &#8213; | &#8628; |         |   |   |
|          |          |         |  &darr;  |         |         |          |          |  &darr; |         |   |   |
|          |          |         |     x    |         |         |          |          |    y    |         |   |   |
|          |          |         |  &darr;  |         |         |          |          |  &darr; |         |   |   |
|          | &#11024; | &#8213; |  &#8213; | &#8213; | &#8628; |          | &#11024; | &#8213; | &#8628; |   |   |
|          |  &darr;  |         |          |         |  &darr; |          |  &darr;  |         |  &darr; |   |   |
|          |    x1    |         |          |         |    x2   |          |    y1    |         |    y2   |   |   |
|          |  &darr;  |         |          |         |         |          |  &darr;  |         |         |   |   |
| &#11024; |  &#8213; | &#8628; |          |         |         | &#11024; |  &#8213; | &#8628; |         |   |   |
|  &darr;  |          |  &darr; |          |         |         |  &darr;  |          |  &darr; |         |   |   |
|    x11   |          |   x12   |          |         |         |    y11   |          |   y12   |         |   |   |


1st.way:
--
$ mkdir x y
$ cd x
$ mkdir x1 x2
$ cd ../..
$ cd y
$ mkdir y1 y2
$ cd y1
$ mkdir y11 y12

2nd.way:
--
$ mkdir x y x/x1 x/2 x/x1/x11 x/x1/x12 y/y1 y/y2 y/y1/y11 y/y1/y12

3rd.way:
--
$ mkdir -p x/2 x/x1/x11 x/x1/x12 x/x2 y/y1/y11 y/y1/y12 y/y2

4th.way:
--
$ mkdir -p x/x{1,2} x/x1/x1{1,2} y/y{1,2} y/y1/y1{1,2}

Absolute path vs Relative path:
----
Absolute path: It is the path from root(/) to destination i.e it is complete path.
Relative path: It is the path from currunt working directory to destination. It is alway retlative to currunt location.

$ mkdir -p x/x{1,2} x/x1/x1{1,2} y/y{1,2} y/y1/y1{1,2}
Assume we are in x11 directory to change to y2 directory:
Absolute path: $ cd /home/satyam/y/y2
               $ ~/y/y2
Relative path: $ ./../../../y/y2
               $ ../../../y/y2

Assume we are in y2 directory to change to x11 directory:
Absolute path: $ cd /home/satyam/x/x1/x11
               $ ~/x/x1/x11
Relative path: $ ./../../../x/x1/x11
               $ ../../../x/x1/x11

Copy command(cp):
---
1. To copy from file1.txt to file2.txt
$ cp file1.txt file2.txt

2. To copy file to directory:
$ cp file1.txt file2.txt file3.txt output

3. To copy all files of 1 directory to another directory:
Assume dir1 contains a.txt b.txt
copy all files of dir1 to dir2
$ cp dir1/* dir2  (but complsury dir1 should be available already)

4. To copy total directories to another directories.
Whenerver we are copying total directories to another directories by usin cd command, we should use -r option(either -r or -R).
$ cp -r dir1 dir2

$ cp dir1 dir2    (if we don't use -r then the follwong error occur)
cp: -r not specified; omitting directory 'dir1'
Note: If the destination directory is already available then total dir1 will be copied to dir2.
If the destination directory dir2 is not already avaible then dir2 will be reated and all files of dir1 will be copied to dir2, but dir1 won't be copied.


Moving and Renaming of directories:
---
both moving and renaming activities can be performed by using single command mv.

1. Renaming of files:
$ mv file1.txt file2.txt            ->    file1.txt will be renamed to file2.txt

2. Renaming of directories:
$ mv dir1 dir2          ->          dir1 renamed to dir2

3. moving of files to some other directory:
$ mv file1.txt file2.txt file3.txt output

4. moving all files of one directories to another directories:
mv dir1/* dir2          -> all files of dir1 will be moved to dir2 after excuting these command dir1 will become empty.

5. moving total directory to another directory:
$ mv dir1 dir2
Note:
If dir2 is not available then renmaing opreation will be performed

Working with files
---
1. creations of files:
In linux we can create files in the following ways:
1. by using touch command
2. by using cat command
3. by using editors like gedit, vi, name etc.

cat command:
--
$ cal > fil1.txt        -> this will overwrite
 some content
 press ctrl+d           -> to save and exit
 
 If fil1.txt is not already  available then it will be created with our provided data.
 If fil1.txt is already available with some data then it will be overwritten with our provided data.
 
Instead of overwriting if we want to append operation then we should use  >>  with cat command.

$ cal >> fil1.txt        -> this will append the data
 some content
 press ctrl+d           -> to save and exit
 
touch command:
--
we can use touch command to create empty file.
$ touch demo.txt  ->    empty file will created.
Q. If we are using touch command but the file already available with some contains then what will happend?
The content of the file won't be changed but last modified data and time(i.e timestamp) will be updated.

Note: we can use touch command for the following 2 purposes:
1.    To crreate an empty file.           2.    To change timestamp of existing file

View or display contents of the file:
--
We can view contents of the files by using the following commands.
1. cat      2. tac      3. rev      4. head     5. tail     6. more     7. less

$ cat < file.txt or $cat file.txt   (< symbol is optional)
while display file contents we can include line no by using -n option.
$ cat -n demo.txt

while display contents we can skip blank lines -b option.
$ cat -nb demo.txt      ->    numbering for blank line won't be there.

We can view multiple files contents at a time by using cat command
$ cat a.txt b.txt c.txt

tac command:
---
It is the reverse of cat. It will display file contents in reverse order of lines i.e 1st line become last line. last line become first line.
$ tac file1.txt

rev command:
--
rev means reverse. There each line contents will be reverse. It is horizintal reverse.
$ rev demo.txt
Note:    cat command will display total file conntent at a time. It is best suitable for small file. If the file cotains 1000 of lines then it is not recommended to use cat command. We should go for head, tail, more and less command.

head command

