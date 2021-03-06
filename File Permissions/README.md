#### File Permissions

File Permissions is the allowed operations by various users with respect to user catogeries.

With respect to file permissions, all users are categorized into the following 4 type:

1.user/owner    -->   represented by 'u'
2.group         -->   represented by 'g'
3.others        -->   represented by 'o'
4.all           -->   represented by 'a'

Permission types:
--
For files and directories, there are 4 types of permissions
1 r    ->    read
2 w    ->    write
3 x    ->    execute
4 -    ->    no permission

| Permission |                                         For Files                                        |                                                                    For Directories                                                                    |
|:----------:|:----------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------:|
| read(r)    | Read Permission of the file means we can view content of the file                        | Read Permission for the directories means we can list out contents of that directories i.e we can use ls command                                      |
| write(w)   | Write Permission of the file means we can modify the content of the file                 | Write Permission for the directory means we can modify contents of that directory i.e we can create a new file and we can delete an existing file etc |
| execute(x) | Execute Permission for the file means we can execute the file just like a normal program | Execute Permission to the directory means we can enter into directory i.e we can use cd command                                                       |


operations related to permission:
--
we can perform the following 3 operations
+   ->    add a particular permission to the  user | group | others | all
-   ->    remove a particular permission to the  user | group | others | all
=   ->    assign a particular permission to the  user | group | others | all

chmod command:
--
xhmod means change mode
we can use chmod command to change file or directory permissions.

syntax:
--
$ chomod <user_catogry><operation><premission>  file name/directory name

eg.
for user add execute permission, for group add write permission and for other remove read permission on the file demo.txt

$ chmod u+x,g+w,o-r demo.txt

note:
Only owner and super user can change file permissions.

How to change permission of existing file.
by using ls command with -l option
$ ls -l demo.txt
-rw-r--r-- 1 satyam satyam 0 Feb 16 00:15 demo.txt
-(type of file/dir)rw-(first three are user permission)r--(next three are group permission)r--(next three are other permission) 1(no of links) satyam(user name) satyam(group name) 0(size) Feb 16 00:15(date creation/modified time) demo.txt(filename/directry name)

user permission + group permission + other permission       order is important
read permission + write permission + execute permission     order is important

$ chmod u+x demo.txt    ->    adding execute permission to the user

$ chmod u+x,g+w,o+r demo.txt  ->  adding write permission to the user, adding write permission to group, adding read permission to other

$ chmod u=rw, g=re, o=r demo.txt    ->    this is the total permission, if any other permission that not specified here, that will be removed ,   so now
user permission     rw-
group permission    rw-
other permission    r--

$ chmod a=- demo.txt    ->    a means all,   so now
user permission     ---
group permission    ---
other permission    ---

$ chmod a=rwx demo.txt    ->    a means all,  giving everyone every permission so now
user permission     rwx
group permission    rwx
other permission    rwx

read permission to the file:
--
If the user has read permission on any file then is allowed to view content to the file i.e can use cat, head, tail, more, tac, rev command.

write permission on the file
--
If the user has write permission on any file then is allowed to perform modification to the content of the file.
If we not having write permission then 
$ cat >> demo.txt
cat : demo.txt : permission denied

execute permission on the file
--
If the user has execute permission on any file then we can execute that file as a program.

myfirstscript.sh
cat > myfirstscript.sh
mkdit d
touch d/unix.txt
exho "learning unixis very very easy" > d/unix.txt
chmod u+x myfirstscript.sh

myfirstscript.sh

note:
--
If we want to execute any file just like a program then compulsary read and execute permission must be required. ececute permission without read permission is useless.



read permission to the directory:
--
If the user has read permission on any directory then he can list out the content of that directories i.e he can use ls command.

write permission on the directory
--
If the user has write permission on any directory then he is allowed to modify to the content of the directory i.e he can add new file and remove existing files.

execute permission on the directory
--
If the user not having execute permission on any directory then he is not allowed to enter into that directory i.e he can't use cd command.

note:
--
If the user not having execute permission on any directory then he can'y perform read and write operation also. because to perrom read and write operation he should enter into the directory which is not possible i.e read and write permission without execute permission on the directory become useless.


#### Linux Vs Security:

The virus file usely created by others. Others are not having write and execute permission on our directory. hence other are not allowed to add virus file to our directires, hence other are not allowed to add virus file to our directories. Hacker are not having execute permission on our directories hence they can't read our file data.
Because of these reaso linux in consider as secure operating system.
Linux follow two level security
1st level   ->    login with credentials
2nd level   ->    file and directroy permission


We are using permission types as r, w and x. These are considerd as symbolic permission, but we can also specify permission by using octal number (base eight) such type of permissions are called numeric permission.

Numeric permission:
--
we can specify permission by using octal number. Octal means base-8 and allowed digit are 0 to 7

0     000   -->     No Permission
1     001   -->     Execute Permission
2     010   -->     Write Permission
3     011   -->     Write and Execute Permission
4     100   -->     Read Permission
5     101   -->     Read and Execute Permission
6     110   -->     Read and Write Permission
7     111   -->     Read, Write and Execute Permission

Note:
---

4 means Read operation
2 means Write operation
1 means Execute operation

It is more eady to remember

5  --->     4+1   --->    r-x
3  --->     2+1   --->    -wx
6  --->     4+2   --->    rw-

Write command for the following permission on demo.txt
for user    ->    Read and Write
for group   ->    Write and Execute
for other   ->    only Write

$ chmod 632 demo.txt
    rw--wx-w-

$ chmod 135 demo.txt
    --x-wxr-x
    
 77 means 077
 $ chmod 77 demo.txt
    ---rwxrwx
   
 7 means 007
 $ chmod 7 demo.txt
    ------rwx
    
 You must have to provide the permissions
 $ chmod demo.txt   -->     we get error
 
 unmask command:
 --
 
 unmask  means user mask i.e hiding permissions.
 Based on unmask default permission will be there for our files and directories.
 
 $ unmask 0022    ->    The default unmask value id 022
 ( the first bit is stick bits that is used by administor)
 The first 0 is sticky bit mostly used in admin related activity
 We have to consider only last 3 digits.
 
 Default premission to the file   -->   666 - unmask value
 i.e  666-022   i.e   644   ( means u -> rw   g ->  r   o ->  r )
 
  
 Default premission to the directory   -->   777 - unmask value
 i.e  777-022   i.e   755   ( means u -> rwx   g ->  rx   o ->  rx )
 
 Q. for newly created files default permission should be 444, then what shuold be unmask value
 Ans.   222   (everyone have read permission)
 
 Based on our requiremnt we can change unmask value
 $ unmask 077
 
 $ touch file1.txt
 
 $ ls -l file1.txt
    rw-------       -> only read and write permission to the user and remaing nothig
    
Note:
--
The mostly used unmask values are 022, 002, 077, 007

022 ->    User has both read and write permission but group and other having only read permission
002 ->    User, group have both read and write permission but other having only read permission
077 ->    User has both read and write permission but group and other have no permission
007 ->    User, group has both read and write permission but other have no permission

To create new user in the existing group

sudo adduser --ingroup durga durga1   -> (here durga is group name and durga1 is the user name)
Now enter your your super user password the durga1 password

Use case
--
durga and durga1 are user belong to the durga group

Note:
--
$ sudo adduser durga2  ( if you don't provide --ingourp then it will create user and group with same name)

$ sudo adduser durga2   -> so it will create a user durga2 in the durga2 group

su - durga1   ->    to switch to durga1 user
