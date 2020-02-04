Q. How to use multiple command in a single line.
---
We can execute multiple independet command in a single line by using the following 2 ways.

1.using semicolon (;)
---

$ cmd1;cmd2;cmd3;...;cmdN    ->  first cmd1 will be executed then cmd2, followed by rest of the command
If any command in the middle, still rest of the command will be executed.

Q. create a dir1, create files a.txt b.txt c.txt in the dir1. write currunt system date and time to a.txt, write currunt calender to b.txt. All these activity we can perform in one line.
----

$ mkdir dir1;touch dir1/{a,b,c}.txt;date >dir1/a.txt;cal b.txt

