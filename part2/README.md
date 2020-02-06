Q. How to use multiple command in a single line.
---
We can execute multiple independet command in a single line by using the following 2 ways.

1st way
--
using semicolon (;)
---

$ cmd1;cmd2;cmd3;...;cmdN    ->  first cmd1 will be executed then cmd2, followed by rest of the command
If any command in the middle fails, still rest of the command will be executed.

Q. create a dir1, create files a.txt b.txt c.txt in the dir1. write currunt system date and time to a.txt, write currunt calender to b.txt. All these activity we can perform in one line.
----
<pre>
$ mkdir dir1;touch dir1/{a,b,c}.txt;date >dir1/a.txt;cal b.txt    ->    valid

$ mkdir dir1;touch dir1/{a,b,c}.txt;Date >dir1/a.txt;cal b.txt    ->    even there 3rd command fails but still 4th command will be executed.
</pre>
2nd way:
---
using &&
---
<pre>
$ cmd1 && cmd2 && cmd3 && ... && cmdN    ->  first cmd1 will be executed then cmd2, followed by rest of the command
If any command in the middle fails, then rest of the command won't be executed.

$ mkdir dir1 && touch dir1/{a,b,c}.txt && date >dir1/a.txt && cal b.txt    ->    valid

$ mkdir dir1 && touch dir1/{a,b,c}.txt && Date >dir1/a.txt && cal b.txt    ->    Here 3rd command fails and hence 4th command won't be executed.
</pre>

command aliasing:
---
alias means other alternattive name or nickname. we can give our more convinent nickname for our linux command aliasing.
Note:
--
we can use type command to chech whether the command is already available or not.
$ type data   -> data is hashed(/bin/date)
$ type sunny  -> bash:type: sunny: not found

How to create alias name?
--
<pre>
$ alias ddd="date;date;date"
While defining alias name before and after = symbol we shouldn't use space.

$ alias ddd = "date;date;date"    &#10008;
$ alias ddd ="date;date;date"     &#10008;
$ alias ddd= "date;date;date"     &#10008;
$ alias ddd="date;date;date"      &#10004;
</pre>
How to list all avaliable aliases:
---
<pre>
$ alias
</pre>
How to remove alias name?
---
<pre>
by using unalias
$ unalias ddd
</pre>
To delete all alias:
---
$ unalias -a

Where we can use alias name?
--
<pre>
1. If any lenghty command repetedly required, then we can create short alias name and we can use that short alias name evertime.
---

$ alias d20f="mkdir dir1;touch dir1{1,20}.txt"
</pre>
To list out all files presence in the present working directory, save these data to 1 output.txt and display no lines to the reminal difeine alias name as cuurnt for this to tal activity?
-----
$ alias currunt="ls > output.txt ;wc -l output.txt"

2.To use other operating systme line window commands directories in linux.
---
<pre>
$ alias cls='clear'
$ alias rename='mv'
</pre>
3.TO handle typing mistakes:
--
<pre>
$ alias grpe='grep'
$ alias gerp='grep'
</pre>
4.To handle language baries:
--
<pre>
In german language dantum means date.
In german language koopy means copy.
$ alias dantum='date'
$ alias koopy='cp'
</pre>
How to presist aliases perminantly:
---
Whenever alias we created , by default available only in the currunt session. once we closed the terminal all aliases will be lost.
But we can make out created alias perminantly in our system by using the following 2 ways.

1st way:
---
<pre>
We have to define our alias in .bashrc file persent in user home directory.
$ gedit .bashrc
add the following lines in the files.
#my own aliases
$ alias ddd="date;date;date"
$ alias cls='clear'

THe file will be executed everytime whenver we open the terminal hence all these alias will be avaiable auto initalize, and we are not required to set everytime.

Note: To refelect these alias, compulsery we have to close and open the terminal.
</pre>
2nd way:
--
<pre>
Instead of editing .bashrc file we can create our own file to maintain user defined alias. The name of the file should be .bash_aliases should be present in user home directory.
gedit .bash_aliases
#my own aliases
$ alias ddd="date;date;date"
$ alias cls='clear'

Note: To refelect these alias, compulsery we have to close and open the terminal.
</pre>

# Regular Expression and wild card character:
---
If we want to represent a group of string according to a perticular pattern then we should go for regular expression.

By using wild card characters we can build regular expression.
<pre>
*             ->    represents zero or more characters
?             ->    represents only one characters
[]            ->    represents range of characters
[abc]         ->    either a and b and c
[!abc]        ->    except a and b and c
[a-z]         ->    any lower case alphabet symbol
[A-Z]         ->    any upper case alphabet symbol
[a-zA-Z]      ->    any alphabet symbol
[0-9]         ->    any digit from 0 to 9
[a-zA-Z0-9]   ->    any alphanumric character
[!a-zA-Z0-9]  ->    except alphanumric character i.e special character
[[:lower:]]   ->    any lower case alphabet symbol
[[:upper:]]   ->    any upper case alphabet symbol
[[:alpha:]]   ->    any alphabet symbol
[[:digit:]]   ->    any digit
[[:alnum:]]   ->    any alphanumric character
[![:digit:]]  ->    anycharacter except
{}            ->    List with comma seperator
</pre>

Examples:
----
1.To list out all files in currunt working directory
---
<pre>
$ ls *
</pre>
2.To list out all files some extension
---
<pre>
$ ls *.*
</pre>
3.To list out all .txt files
---
<pre>
$ ls *.txt
</pre>
4.To list out all files that start with a and end with t
---
<pre>
$ ls a*t
</pre>
5.To list out all files where file name contains only 2 character and start with a
---
<pre>
$ ls a?
</pre>
6.To list out all files contains exactly 3 character
---
<pre>
$ ls ???
</pre>
7.To list out all files that contains atleast 3 character
---
<pre>
$ ls ???*
</pre>
8.To list out all files where file name start with a or b or c
---
<pre>
$ ls [abc]*
</pre>
9.To list out all files where file name shouldn't start with a and b and c
---
<pre>
$ ls [abc]*
</pre>
10.To list out all files start with lower case
---
<pre>
$ ls [[:lower:]]*   or     $ ls [a-z]*
</pre>
11.To list out all files start with upper case
---
<pre>
$ ls [[:upper:]]* or $ ls [A-Z]*
</pre>
12.To list out all files start with digit
---
<pre>
$ ls [[:digit:]]*   or     $ ls [0-9]*
</pre>
13.To list out all files where 1st letter should be uppercase alphabet 2nd letter should be a digit and 3rd letter should be lower case allphabet
---
<pre>
$ ls [A-Z][0=9][a-z]  or    $ ls [[:upper:]][[:digit:]][[:lower:]]

note: curruntly $ ls [A-Z][0=9][a-z] is not working on ubuntu but $ ls [[:upper:]][[:digit:]][[:lower:]] works perfectly
</pre>
14.To list out all files start with special symbol
---
<pre>
$ ls [!a-zA-Z0-9]*    or    $ ls [![:alpha:]]*
</pre>
15.To list out all files start with .java and .py extension
---
<pre>
$ ls {*.java,*.py}          ->    there should be no spaces in the middle

</pre>
Note:
---
We can use regular expression and wild card characters with the following command also    cp, mv, rm etc.
16.To copy all files start with digit to dir1 directory
---
<pre>
$ cp [0-9]* dir1    or    $ ls [[:digit:]]* dir1
</pre>
16.To move all files start with alphabet and end with .txt to dir1 directory
---
<pre>
$ mv [a-zA-Z]*.txt dir1    or    $ mv [[:alpha:]]*.txt dir1
</pre>
17.To remove all files start with a or b or c and end with et
---
<pre>
$ rm [abc]*[et]
</pre>
18.write command that will display contents of all files that begins with digit and end with vowel
---
<pre>
$ cat [[:digit:]]*[aeiou]
</pre>
19.write command that will display contents of all files that begins with lower case alphabet symbol and has d at the 3rd character postion and end with an upper case aphabet symbol
---
<pre>
$ cat [[:lower:]]?d*[[:upper:]]   or $ cat [a-z]?d*[A-Z] 
</pre>
20.write command that will list out all .jpg files in Pictures directory
---
<pre>
$ ls /home/satyam/Pictures/*.jpg    or    $ ls ~/Pictures/*.jpg 
</pre>


## locate command
---
We can use locate command to locate files and directories in our system. Internally locate command will search in the database fir the required files and directories and return the result.
As locate command searching in the database instead of file system performance will be improved.
1.To locate all .jpg files:
---
<pre>
$ locate *.jpg
</pre>
2.To ignore case:
---
by default locate commad will consider case. if we want to ignore case we have to tuse -i option
<pre>
$ locate -i *.jpg
</pre>
Note: in ubuntu -i is not working
3.To limit no of lines in the result
---
<pre>
$ locate --limit 5 *.conf
</pre>
4.To --existing   or  -e
---
before display ruselt to check wheter the file exists or not we have to use --existing or -e
<pre>
$ locate --existing *.jpg
</pre>
reason:
----
locate command internally uisng database to find the result. These databasea will be updated only once per day. by default after updiating database some files may deleted hence before printing results to check whether files are existing or not, we have to use -e or --existing.
5.To --follow     or    -L
---
before displaying the result to check whether symbolic links pointing to origanal files or not, we have to use -L or --follow option. then broken symbolic links wouldn't be display in the output
<pre>
$ locate --follow *.txt     or      $ locate -L *.txt
note:   wecan use all these option together
$ locate --existing --follow -i --limit 5 *.txt 
</pre>
6.How to update database ?
---
we can see database used by locate command with -S option
<pre>
$ locate -S
This database will be update only once per day if we are creating or removing any directories then to reflect changes we have to update databaae expilictly, by using updatedb command, but admin privilage must be required.
$ sudo updatedb
</pre>

## find command
---
<pre>
we can use find command to find files and directories persent in our system. It provides more search option when comapred with locate command like
1.search for only files
2.search for only directories
3.search for name
4.search for size
5.we can search result automaticaly for some other commands
6.we can restrict maxdepth
etc
$ find    ->    it will find all files and directories in currunt working directory and below in linux file system. This is the default behaviour
$ find /dev       $ find /etc
</pre>
maxdepth optioin
---
<pre>
usually find command will search in all depth levels. but we can specify the required depth level by using maxdepth option.
$ find -maxdepth 2      ->    to limit depth
$ find -maxdepth 100    ->    limit to 100 depth if that not case it won't through any error
</pre>
note:
---
for max depth option we should use single hyphen(-) but not double hyphen(--)
