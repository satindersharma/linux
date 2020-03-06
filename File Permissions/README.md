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



