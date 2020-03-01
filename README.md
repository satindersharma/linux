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
--
We can use head command to view top few lines of contents. 
$ head demo.txt         ->          It will display top 10 lines of demo.txt 
$ head -n 5 file.txt    or    $ head -n 5 file.txt    -> to display top 5 lines of file. Instead of 5, we can use any no. 
$ head -n -5 file.txt   ->          To display all lines of file.txt except last 5 lines. 
$ head -c -5 file.txt   ->          To display first 5 characters of file.txt i.e to display first 5 bytes of the file. 
Note:       In linux each character, every character requires 1 bytes of memory hence the no of character and no of bytes are same. 

tail command:
--
We can use tail command to view few lines from bottom of the file. It is opposite to head command. 
$ tail file.txt         ->          To display last 10 lines. 
$ tail -n 5 file.txt    or       $ tail -5 file.txt   or            $ tail -n -5 file.txt       ->          Display last lines 
$ tail -c -5 file.txt         ->          It will display last 5 character of the file i.e it will display last 5 bytes content of the file. 

more command:
--
By using command we can view file content page by page only in forward direction. 
$ more file.txt 
It will display 1st page,  
enter key         ->    to view next line 
spacebar key      ->    to view next page 
q key             ->    to quit 

$ more -d file.txt      -d    option means for providing details line 

less command:
--
By using more command we can view file content page by page only in forward direction. If we wnat to move either in forward direction or in backword direction then we should go for less command.  
$ less command          ->          It will display 1st page by default  
d           ->          to go to next page(d means down)  
b           ->          means backword direction(b means backword)  
q           ->          to quit  

Q. Assume a file content enough data . write command to display from 3rd line to 7th line.  
$ head -7 file.txt | tail -5  

Creation of hidden files and directories:
---

If any file start with . (dot) such type of file is called hidden file. If we don't want to display te files in normal listing then we have to go for hidden files. Hdden files are ment for the the hiding data. All system files which are internally required by kernal are hidden files.
We can create hidden files just like normal files. Only difference is file name should start with . (dot)
$ touch . db_info       $ cat . db_info
Even by using editor also we can create hidden files.
we can create hidden directories also just like normal directories.
$ mkdir .db1

note:
--
By using hiden file and directroies we may not get full security.
To make more secure we hoave to use proper permissions.
For this we should use
interconversion of normal file and the hidden files based on our requirment.
we can convert normal file as hidden file and vise virsa
$ mv demo.txt .demo.txt       ->          converts normal file to hidden file
$ mv .demo.txt demo.txt       ->          converts hidden file to normal file

comparison of files:
---
we can compare data of the files by using the following commands.
1. cmp            2. diff     3. sdiff          4. vimdiff        5. comm

cmp command:
--
It will compare bytes by bytes.
$ cmp file1.txt file2.txt           ->          If the content is the same then we won't get any output. If the content is different then it provides information about only first differnce. byte no and line no will be provided.
$ cmp a.txt b.txt
note:
--
cmp command don't show all differnce and show only first difference.

diff command:
--
It will show all differnce in the content.
$ diff file1.txt file2.txt           ->         If the content is same no output. If the content is different then it will show all diffrences
for the diff command we can use the following option:
-q show message when file are differnt
-s shows message when files are same or identical
-y show comparision line by line (parllel comparision)
$ diff -q file1.txt file2.txt
$ diff -s file1.txt file2.txt
$ diff -y file1.txt file2.txt

If we want to suppress command lines then we should use
--suppress -common-lines option with -y option
$ diff -q --suppress -common -lines file1.txt file2.txt

sdiff command:
---
we can use sdiff command for side by side comparision or parllel comaprision

$ sdiff a.txt b.txt

Note:
--
sdiff command and diff command -y option are same.

vimdiff command:
---
It will highlight difference in the vim editior. vim editor is advance version of vi editor. by default vim is not availbale in ubuntu. we have to install sepratorly.
$ sudu apt install vim
$ vimdiff a.txt b.txt
ctrl+w+w  -->           to goto next wondow
:q        -->           close currunt window
:qq       -->           close all window
:qq!      -->           close all window forcefully

comm command:
--
By using comm commnd we can campare data of two files.
$ comm file1.txt file2.txt    ->    It will display result in 3 columns.


##### Creation of link files:

There are two types of link files:
1. Hard link files            2. soft link file

Hard link file:
---
It is just another name of the same exact file.
We can create hard file file by using ln command.
$ ln orignal_file hard_link_file
example:
$ ln abc.txt abcln.txt        ->          abc.txt is the orignal file and abcln.txt is the link file

Important conculsion about hard link file:
---
1. Both origanl and hard file have the same node no, same size and some timestamp
2. If one delete orignal file then there is no effect on hard link file.

soft link file:
---
A soft link is a pointer to another file. It is just like window's shortcut.
Itis also known as symbolic link.

We can create soft link file by using ln -s (with -s option)
ln -s orignal_file soft_file

eg:
$ ln -s abc.txt abcln.txt           ->          Here abc.txt is original file where abcln.txt is soft link files.

Important conculsion about soft link file:
--
1. orignal and soft file have the diffrent node no, defferent size and different timestamp
2. Usally soft link file have smaller file size then orignal file size.
3. If on delete orignal file then soft line file will become useless.

link file for directories:
--
We can't create hard link for directories becouse it breaks linux file system. Having 2 root directories is meaningless
$ ln dir1 dirln
ln : dir1: hard link not allowed for directories
but we can create soft link fo directories
$ ln -s dir1 dirln
Note:
--
for files we can create both hard and soft link but for directories we can only create soft link. 
If we perform any change to the content of orignal file then these changes will be reflected in the link file, similarly if we perform any change to the link file then those changes will be refelcted to the origanl file. 
This is true for both soft and hard link file. 

word count command(wc):
---
We can use wc command to count no of lines, words and characters present in the given file.
$ wc file.txt
no_of_lines no_of_words no_of characters filename
$ wc abc.txt
4 16 76 abc.txt
we can use the following option:
-l    ->    to print only no. of lines
-w    ->    to print only no. of words
-c    ->    to print only no. of characters
-lw   ->    to print only no. of lines and words
-wc   ->    to print only no. of words and characters
-L    ->    to print no of characters present in longest line

We can wc comment for multiple files symountanouly
$ wc abc.txt demo.txt
   4 78 90 abc.txt
   3 7 93 demo.txt
   7 85 183 total

Sorting content of the file:
--
We can short data of the file by using sort command.
$ short a.txt
If we want to sort based on reverse of alphabetical order, we have to use -r option
$ short a.txt
Note: If th efile contains alphanumeric data then first numbers will be consider and then alphabet symbols
If file contains only numbers then sorting is not based on numeric value but if just based on digit(i.e just first number)
cat a.txt               sort a.txt                    sort -n a.txt
11                      11                            2
2                       2                             7
7                       222                           9
222                     7                             11
9                       9                             222
If we want to sort based on mumeric, then we have to use -n option, -n means numeric value
by default sort will display duplicate values, If we want only unique lines then we have to use -u option
$ sort -u a.txt
Note: We can also use -ur, -ucn, -unr option also.

To play with unique data, there is speicaal command available uniq
Sorting tabular data by using -k option:
---
-k means KEYDEF (key defination) Based on which key (column) we have to sort.
sort based on file size in accending order
$ ls -l /etc | Head | sort -k 5n          (5(5th column)n(numeric value))
sort on based on month
6th column provides total date, if we want to consider only month then we should use -k -6M
$ ls -l /etc | Head | sort -k 6M          (6(6th column)M(Month))
sort based on no of links in decending order
$ ls -l /etc | Head | sort -k 2nr          (2(2th column)n(numeric value)r(reverse))

find unipe content in the file by using uniq command
We can use uniq command to display unique in the file, but to use uniq command complsury file should be sorted. Othervise it won't work.
uniq a.txt              It won't work
sort a.txt | uniq       it works beause uniq work on sorted data

with uniq command we can use the following option:
---
-d          ->          To display only duplicate lines
-C          ->          To display no. of occurance of each lines
-c          ->          Ignore case while computing
-u          ->          To display only unique lines i.e the lines are duplicated

sort a.txt | uniq -d
sort a.txt | uniq -C
sort a.txt | uniq -c
sort a.txt | uniq -u

#### input and output of commands:

|                               |         |                            |
|------------------------------:|:-------:|----------------------------|
|      Standard Input(0) &rarr; |         | &rarr; Standard Output(1)  |
|                               | Command |                            |
| Command Line Arguments &rarr; |         | &rarr; Standard Error(2)   |


commands can take some input, perform required option and produces some output
while excting command if anything goes wrong we will get error message.
commands can take input either form standard input device or from command line arguments. commands will procude results either to the standard output or standard error.
Standard input, Standard output and Standard error are data streams and can flow from, palace to another place hence redirection and piping concepts are aplicable.

command line argument are static
----
and  these(comand line arguments) are not streams. hence redirection and piping are not applicable.

These data streams are associated with some numbers.

Standard input associated with 0
Standard output associated with 1
Standard error associated with 2

By default:
Standard input connected with keyboard
Standard output connected with console/terminal
Standard error connected with console/terminal

Standard input to the keyboard and output to the device:
for cat command if we are not provides any arguments, then the input will be taken from standard input device (keyboard) and display the output to the standard output device(terminal)

$ cat
this        ->    it will take input from keyboard
this        ->    it will display output to terminal
|           ->    wiating for input
(press ctlr+d)

input from command line arguments and error message to the standrad error:
--
We have to provides file name of command line arguments to run command, if the specified file not availble then we will get error message. Ehich eill display to standard error hence which is nothing but console.
$ rm file1000
rm: cannot remove 'file100' . No Such file or directory
note:
--
some command may except any standard input and some command may except command line arguments and some may except both.
cat command can except input form standard input device and from command line arguments.
rm command will always accept only command line argument
echo command will accept only command line arguments.

##### Redirection:
As standard input standard output and standard error are data sream and can flow from 1 place to another place. we can redirect these streams based on our requirment.

redirecting Standard Output:
--
By default standard output connected to terminal or console/terminal
but we can redirect to new destination. we can perferm output redirection by using > or >> symbol

>           ->          will perform overwritting of existing data
>>          ->          will perform appending to existing data

eg. To redirect standard output of cat command from terminla to output.txt
$ cat 1> output.txt           ->          here 1 associated to standard output
hello there
ctrl+d
The output won't display to the terminal and will be written to output.txt

Note:
--
Redirection symbol > and >> is always associated with 1 by defalut hence we are not required to specify explicitily
cat >> output.txt
there is
ctrl+d

Redirecting Standard Error:
--
By default standard eror attached to terminal but based on our requirement we can redirect from terminal to another new destination. We can perform error redirection by using > and >> symbol
$ rm file100 2> error.txt           ->          now error message won't dislay to the terminal and will be directed to error.txt
Note:
--
for error redirection 2 is mendatory
If output and error redircting to the same destination, we can write command as follow
$ rm file100 &> output.txt          ->          & means both output and error redirection

redirection Standard intput:
---
By default standard intput attached to keyboard but based on our requirement we can redirect from keyboard to another new destination. We can perform input redirection by using < symbol

$ cat 0< a.txt 1> output.txt 2> error.txt

< symbol is always associated with 0 by default hence we can ignore it

$ cat < a.txt > output.txt 2> error.txt

tty:
---
tty         ->          this will display file related to the currunt terminal

redirecting Standard Output from 1 terminal to another terminal:
--
In unix evertyhing is treated as file even terminal also. we can find terminal related file by ysing tty command
termianl 2:
$ tty       ->          /dev/pts/1
terminal 1:
$ echo "hello l love You" > /dev/pts/1
$ clear > /dev/pts/1

How to ignore standard output and error message:
--
We have to redirect to new device which is representd by /dev/null 
$ cat a.txt > /dev/null
$ rm file100 > /dev/null

#### Piping:
Sometimes we can use output of one command as input to another command.
This concept is called piping.
By using piping concept multiple command will work together to fulfil our requirement.

|              |           |               |              |           |                     |
|-------------:|:---------:|---------------|-------------:|:---------:|---------------------|
| input &rarr; | command 1 | output &rarr; | &rarr; input | command 2 | &rarr; final output |

We can impliment piping by using virtical bar ( | )

eg 1:
$ ls -l /etc | wc
215 1938 11896
(first ls command exicuted and output of this command witll become input to wc command.)
$ ls -l | more          (page by page)
(first ls command execute and output of this command will be input for more command)

$ ls -l /etc | wc | wc -l           ( output will be 1)

Requirment:
--
The output of ls command should be saved to output.txt and should be provided input to wc command.

$ ls -l > output.txt | wc -l                    &#10008;

This command won't work because if we are using redirection in the middle of piping, It will break piping concept.
In piping If we want to save the output of one command to a file and if we want to pass that output as input to next command symuntanoulsy, then we should go for tee command.

tee command:
--
tee command is just like T-Junction or T-Pipe, It will take one input but provides two outputs.

$ ls -l | tee output.txt | wc -l

tee mostly used to just save and send to the next command


|            |                            |             |                                              |    |
|------------|----------------------------|:-----------:|----------------------------------------------|----|
| ls command | &rarr; output of ls &rarr; | tee command | &rarr; send output of ls commad to wc &rarr; | wc |
|            |                            |    &darr;   |                                              |    |
|            |                            |    &darr;   | save output of ls to output.txt              |    |
|            |                            |  output.txt |                                              |    |


