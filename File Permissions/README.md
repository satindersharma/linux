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
