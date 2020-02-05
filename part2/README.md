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

