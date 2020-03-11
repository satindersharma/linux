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

