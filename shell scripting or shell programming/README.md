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

/etc/shells   file contains all available shells information

$ cat /etc/shells
/etc/shells   :   valid login shells
/bin/sh
/bin/bash
/bin/rbush
/bin/dash

How to switch to other shells:
--
Based on our required we can switch from 1 shell to another shell
switch sh shell      ->     $ sh         exit from sh shell and back to default shell       ->      $ exit
switch rbash shell   ->     $ rbash      exit from rbash shell and back to default shell    ->      $ exit
switch dash shell    ->     $ dash       exit from dash shell and back to default shell     ->      $ exit

What is shell script:
---
A gruop of command save to a file and this file is nothing but shell script. Inside shell scripts, we can aslo use programming features like condtional statment, loops, function etc
Best suitable for system activity and automation activities.

#### How to write and run shell script:
--

step 1. write the scripts
--

test.sh
---
echo "this is first script"
echo "this month calender"
cal

step 2. provides exicute permission to execute scripts
--
$ chmod u+x test.sh

step 3. Run the script:
--

$ /bin/bash /home/durga/test.sh   ->  defining to shell and script file path

$ bash /home/durga/test.sh        ->  we can  use only shell name also and script file path

$ bash ./test.sh               ->  we can use only shell name also and as . means present working directory so we can use this form also

$ ./test.sh                  ->  as default shell is defined so we need only to pass script file path

Note:
--
The default is bash hence bash is reponsible to execute script. Instead of bash if we want to use bourne shel(sh) then we have to ue the following command


$ /bin/sh /home/durga/test.sh

$ sh /home/durga/test.sh

$ sh ./test.sh

#### Importance of sha-Bang:

By using Sha-Bang we can specify the interpreter which is responsible to execute the script

here:     #         ->      sharp       and     !       ->        Bang
#!    ->    sharp bang      or    shabang   or    shebang

eg:
--
#! /bin/bash            ->    It means the scripts should be executed by bash shell
#! /bin/sh              ->    It means the scripts should be executed by bourne shell
#! /usr/bin/python3     ->    It means the scripts should be executed by python3 interpreter

If we write sha-bang in our script at the time of execution we are not required command to execute, and we can execute script directly.

Write a python program/script and execute with and without sha-bang

test.py
--
#! usr/bin/python3

import random
name = input("enter name")
l = ['sunny','bunny',chinny']
print("hello", name)
print("conratulation.. you are going to marry",random.choice(l))

without shabang:
--

$ /usr/bin/python3 /home/durga/test.py

$ python3 ./test.py


with shabang:
--

$ /home/durga/test.py

$ ./test.py

Q. Consider the following
--
demo.sh
--

#! /bin/rm

echo "it is beautiful script"

If we execute this script what will happen

$ ./demo.sh

It is equvilent to rm ./demo.sh
so demo.sh will be removed

#### How to execute our script from anywhere in our system

(it better to keep all your file to a folder and as the file exetension is not required still .sh file convetion is widely used to create the scripts)

$ mkdir scripts
mv test.sh scripts/
export PATH=$PATH:/home/durga/scripts

for any command or script by default shell will check location specified by path variable

If we add our scripts location to PATH variable value, then we can run our scripts from anywhere in our system.
we can do this in the following 2 ways.

1.Session Level:
--
$ export PATH=$PATH:/home/durga/scripts
$ echo PATH         ->      To check that our path is added or not

Now we can run our scripts from anywhere directly and we are not required to provide either absolute path or relative path

$ test.sh

Note:
--
This way of setting PATH variable is applicable only for current session. once we close the terminal then automaticaly the changes will be lost.

2.Setting PATH permanently at user level:
--
In our user home directory there is a file named with .bashrc. This file will be execute automatically whenever we open the terminal.
If we define PATH variable in this file then the value become permanent and we are not required to set every time.

$ gedit .bashrc

and the following line at the bottom of files(.bashrc)
export PATH=$PATH:/home/durga/scripts

Q. What is the meaning of startup files?
--
.bashrc is the startup file and will be execute automaticaly at the terminal starting,, hence if we want to perform any activity while starting the terminal then we have to define that activity inside this file.

eg.         creating aliases, updating PATH variable values etc

Variables:
--
Variables are placeholder to hold our values. variables are key value pair. In shell programming there are no data types, every value is treated as text type or string type.

All variable are divided into 2 types:

1. Environment variables/predefined variables
2. user defined variables

1.Environment variables:
--
There are predefined variables and mostly used internally by the system. Hence there variable also know as system variables.

But basaed on our requirment, we can use this variable in our scripts
we can get all environment variable information by using either env command or set command

$ env
$ set

How to change prompt:
--

internally PS1 environment variable is responsible to display terminal promt, by reassign this variable value we can change the  prompt

durga@durga-VirtualBox:~$ PS1=sunny$
sunny$        ->        durga@durga-VirtualBox:~ is definedin PS1 variable

demo scripts to use some environment variables

env.sh
--

#! /bin/bash

echo "user name:$USER"
echo "user home directory: $HOME"
echo "user currunt working directory$PWD"
echo "default shell:$SHELL"
echo "path location:$PATH"

user defined variables:
--

Based on our programming requirment we can define our own variables also such types of variables are called user defied variables.

$ USER=Dhoni
$ echo "Hello $USER"      ->      Hello Dhoni

Rules to define variables:
--

1. It is highly recommanded to use only uppercase charcters.
2. If variable contains multiple words then this word should be seperated with underscore.
3. variable names can't start with digit
4. we can't use special symbol line    -,@,# etc

How to define read only variables:
---

we can defaine readonly varaibles by using readonly keyword
$ x=5
$ readonly=x
$ x=100         ->      x readonly variable

If variable is readonly then we cannot perform reassignment for that variables and it will become constant

variables scripts:
---

There are 3 scopes available for variables.

1. session scope
2. user scope
3. system scope

1.session scope:
--
The variable which are declared in the terminal are said to be in session scope. Once we close the terminal (i.e currunt session) automatically all varibles will be gone.
$ x=10
$ y=18
This are session scope variable

2.user scope:
--
The variable which are declared inside .barshrc file are said to be in user scope.

These variable are available for all session related to currunt user.
These variable can't be accessed by other user.

.bashrc
--

export GEUST=Dhone
export FRIEND=kholi

#### note:
The changes will refelected only when we restart the terminal as we have edited the .bashrc file and these file run when terminal start.
in case of user scope, If you switch to another user it won't work

3.system scope:
--
If the variable available for all user and for a sessions, such type of variable are said to be in system scope.

We have to declare these variables inside /etc/prfiles file
but to edit this file compulsary root permission must required.
( the porfile file is a system file so a normal user can't modify only root user can do that)

$ sudo gedit /etc/ profile
export HERO=MSDhoni
export HEROINE=sunny

#### note:
The change will reflected when the system restart as /etc contains system configurationn file and we have edited these files. so restart is required
(to reflect the changes we have to restart our virtaulmachine)

Variable Substitution:
--
Accessing the value of a variable by using and symbol is called variable sustitution

syntax
$variablename
$(variablename)

Recommended way is $(variablename)

test.sh
---
#! /bin/bash

a=10
b=15
course=linux
ACTION=SLEEP
echo "the value of a and b is $a $b"
echo "my favourite action is $ACTIONING"
echo "I Love ${ACTION}ING

output
--
the value of a and b is 10 15
my favourite action is 
I Love SLEEPING


consider the following variable declartion:
---
NAME="UNIIX"         &#10004;
NAME='UNIIX'         &#10004;
NAME=UNIIX           &#10004;

To print variable NAME:
---
echo NAME           &#10008;
echo $NAME          &#10004;
echo '$NAME'        &#10008;
echo "$NAME"        &#10004;

While performing variable substitution , we can't use single quotes but we can use double quotes.

command substitution:
--
We can execute command substitution and we can substitute its results based on our requirment, this concept is called substitution
syntax:
--
old style:   `command`   (These are backquotes but not sigle qoutes)
new style:    $(command)  

eg:
"today date `date +%D`"   ->    old style
"today date $(date +%D)   -?    new style
eg:
echo "Files in currunt workind directory is : `ls | wc -l`"
echo "Files in currunt workind directory is : $(ls | wc -l)"

Command Line Arguments:
--
The arguments which are passing from the command promt at the time of exection are called command line argumetns.

$ users.sh 10 20 30     ->    10 20 30 are command line arguments

inside the scriptw ecan access command line arguments as follow

$#    -->   Number of arguments
$0    -->   script/file name
$1    -->   First argument
$2    -->   Second argument
$3    -->   Third argument
$@    -->   All Arguments(It behave like seperated argument)
$*    -->   All Arguments(It behave like one single argument)
$?    -->   Represets exist code of Previously executed command or script

Differece between $@ and $*
--
$@ all command line arguments with space seperator:       "$1" "$2" "$3" "$4" "$5"
$* all command line arguments as single string where C is the first character of the internal field seperator
IFS   "$1c$2c$3c$4c$5"
