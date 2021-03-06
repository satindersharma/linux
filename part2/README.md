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

file type by type:
---
we can find only files or only directories by using type.
-type f   ->    means only files
-type d   ->    means only directories

$ find -type f
$ find -type d

Note:
--
we can use -maxdepth and -type option symntanously
but we should use first -maxdepth and then -type, otherwise we will get warnigs.
$ find -type f -maxdepth 2      ->    generate warning    &#10008;
$ find -maxdepth 2 -type f      ->    no warning          &#10004;

file type by name:
--
we can find file and directories by name by using -name option
$ find -name 'A.txt'
$ find -name '?.txt'
if we pass $ find -name ?.txt instead of $ find -name '?.txt'   it give error.

file type by size:
---
we should use -size option:
  + symbol means greater than
  - symbol means less than
  
1.To list out all file where file size is over 200kb
--
<pre>
$ find / -type f -size +200k | wc -l
</pre>
2.To list out all file where file size is less then 200kb
--
<pre>
$ find / -type f -size -200k | wc -l
</pre>
3.To list out all file where file size is 200kb
--
<pre>
$ find / -type f -size 200k | wc -l
</pre>
4.To list out all file where file size is greater then 200kb but less then 4MB
--
<pre>
$ find / -type f -size +200k -size -4M | wc -l
</pre>
5.To list out all file where file size is greater then 200kb but less then 4MB
--
<pre>
$ find / -type f -size +200k -size -4M | wc -l
</pre>
6.To list out all file where file size is less then 200kb but more then 4MB
--
<pre>
$ find / -type f -size -200k -size +4M | wc -l      &#10008;
This give output 0
It will find all files where file size is less then 200kb but more then 4MB, there is no chance of existing such type of file. henc answer is zero.
</pre>

-empty option:
---
To find only empty files and directories
$ find -type f -empty   ->      It will list all empty files.

how to use search result of find command:
--
we can perform any expression like cp mv rm etc on the result of find command. for this we have to use -exec option.
-exec means execution:
To copy all files present in etc folder where file size is less than 2kb to dir1 present in desktop.
<pre>
$ find /etc -type f -size -2k -exec cp {} dir1 \;
</pre>
(\; must use the backward slash and semicolon to end the execution)
before performing required copy operation if we want confirmation then we should use -OK option in palace of -exec option
<pre>
$ find /etc -type f size -2k -OK cp {} dir1 \;
</pre>

### difference bitween find and locate command:

|                                                 find                                                 |                                                       locate                                                      |
|:----------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------:|
| It searches directories in the file system for the required files and directories                    | It searches in the database for the required file and directories                                                 |
| find command has number of options and easy to cutomise based on our requirement                     | locate command has very few option                                                                                |
| we can find file based on name, type, size, depth, age, user, group and permission                   | we can find files only based on name and permission                                                               |
| we can reduce the depth of search                                                                    | we can't reduce the depth of search                                                                               |
| find command won't produce deleted files in search result as it searches directly in the file system | locate command may produce deleted files in search result as it searches in the database which may not be updated |
| These is a way to use search result by using -exec option                                            | There is no directly way to use search result                                                                     |
| find command operates slowly                                                                         | locate command operates fastly                                                                                    |


## Compression and Uncompression of files (tar, gzip, gunzip, bzip2, bunzip2)
Its a part of admin activity. it is very common requirment to pack and commpress a group of files. The main advantage are:
1.It improves memory utilization
2.Transpotaion will become very easy.
3.It reduces download times  -etc
These process involves the following two activites
1.creation of archive files
2.Applying Compression algorithim on that archive file

#### Creation of Archive files:

We can group multiple files and directories into a single archive files by using tar command.
tar   -->     tape archive

1.To create tar file:
--
<pre>
$ tar -cvf demo.tar file1.txt file2.txt file3.txt
$ tar -cvf demo.tar *
</pre>

2.To display table of content of tar file:
--
<pre>
$ tar -tvf demo.tar
</pre>

2.To extract of content of tar file:
--
<pre>
$ tar -xvf demo.tar
</pre>

#### Compression algorithm on the tar file:
There are multiple compression and decompression algorithm
1. gzip   ->    less compression but more performance
2.bzip2   ->    more compression but less performance

Compression and decompression by using gzip
---
1.To compress tar file:
--
<pre>
$ gzip demo.tar       ---->         demo.tar.gz
</pre>
2.To uncompress gz file:
--
<pre>
$ gunzip demo.tar.gz       ---->         demo.tar
</pre>


Compression and decompression by using bzip2
---
1.To compress tar file:
--
<pre>
$ bzip2 demo.tar       ---->         demo.tar.bz2
</pre>
2.To uncompress gz file:
--
<pre>
$ bunzip2 demo.tar.bz2       ---->         demo.tar
</pre>

##### How to create a tar file and compress in a single command  (use z and j in tar command)
###### By using gzip compression algorithm
1.To create tar file and perform compression:
--
<pre>
$ tar -cvzf demo.tar file1.txt file2.txt file3.txt    (this will create and commpress and return demo.tar.gz)
</pre>


2.To uncompress and extract of content of tar.gz file:
--
<pre>
$ tar -xvzf demo.tar.gz          (this will uncompress and extract and return demo content)
</pre>

###### By using bzip2 compression algorithm
1.To create tar file and perform compression:
--
<pre>
$ tar -cvjf demo.tar file1.txt file2.txt file3.txt    (this will create and commpress and return demo.tar.bz2)
</pre>


2.To uncompress and extract of content of tar.bz2 file:
--
<pre>
$ tar -xvjf demo.tar.bz2          (this will uncompress and extract and return demo content)
</pre>

#### grep command
grep stand for 
globally search a regular expression and print it
global regular expression print
global regular expression parser
We can use grep command to search for the given pattren in a single or multiple files.
It prints all matched lines.


1.To search data in a single file:
--
<pre>
$ grep "Durga" subjects.txt
$ grep Durga subjects.txt
It prints all matched lines. This line which contains mached pattrens.
</pre>

2.To search data in a mulitple file:
--
<pre>
$ grep "Durga" subjects.txt subjects2.txt
$ grep Durga *
It ignore directroies and only in the file it will search.
</pre>

3.To search data by ignoring case:
--
<pre>
$ grep -i "Durga" subjects.txt
It ignore case.
</pre>

4.To display no of occurance:
--
<pre>
$ grep -c "Durga" *.txt
</pre>

5.To display line no before result:
--
<pre>
$ grep -n "Durga" *.txt
</pre>

6.To display filename in which pattren present:
--
<pre>
$ grep -l "Durga" *.txt
</pre>

7.To print all lines except matched lines:
--
<pre>
$ grep -v "Durga" *.txt
</pre>

8.To search for exact word in the file:
--
<pre>
$ grep -w linux demo.txt
</pre>

9.Display before, after and surrounding line including matched pattren:
--

we have ot use -A, -B and -C option
-A means After
-B means Before
-C means Before and After
<pre>
$ grep -A 'linux' demo.txt
$ grep -B 'linux' demo.txt
$ grep -C 2 'linux' demo.txt    (It will display matched pattern with two above and below lines of that pattern. Here -C is optional)
$ grep -2 'linux' demo.txt
If we are not specifiing A,B,C option explicitly by default C will be considered.
</pre>

Search for multiple content in the given file.
---
<pre>
$ grep -i -e 'python' -e 'java' demo.txt
</pre>
egrep:
---

Instead of using -e option we can use egrep command directly. It is extended grep. It interpret pattrens as extended regular expression.
<pre>
$ egrep -i "(java | python)" subject.txt
</pre>

grep      ->    regular expression but not all pattrens
egerp     ->    all pattrens
fgrep     ->    fixed string only

grep with -F option or fgrep:
---
fgrep     ->     fixed string global regular expression print.
It will take a group of fixed strings and search for these in the given file.
<pre>
$ grep -F "java
>python
>Unix" subjects.txt
</pre>
Insead of using -F option we can use fgrep command directly.
<pre>
$ fgrep "java
>python
>Unix" subjects.txt
</pre>


grep vs egrep vs fgrep:
---
Noreaml grep can undersatand regular expression but not every pattren. But egrep can understand regular expression and every pattren.
[0-9]   ->    This regular expression can be understand by grep and egrep command.
(java|linux)  ->  This regular expression can be understand by only egrep but not grep command.
fgrep can be used only for fixed number of string and cannot be used for regular expression.

To display matched pattren instead of total lines:
--
<pre>
$ grep -o c[aeiou]ll demo.txt   -> this wil preint a=only matched pattren(like call cill coll etc)
</pre>

Q. Write grep command to extract only mobile no and save to moblie.txt
--
<pre>
$ grep -o '[0-6][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]' input.txt > mobile.txt
$ grep -o '[0-6][0-9]{9}' input.txt > mobile.txt    -> it won't work      grep command don't understand {9}
$ egrep -o '[0-6][0-9]{9}' input.txt > mobile.txt
</pre>

To search into all files inside a directory (by using -F):
---
<pre>
$ egrep -o -R '[6-9][0-9]{9}' resumes
</pre>

###### Assignment1:

###### Save all running process information inside a file named with result.txt
<pre>
$ Ps -ef > results.txt
</pre>
Display all lines which  contains 'lib'
---
<pre>
$ grep 'lib' results.txt
</pre>
Display all lines which dosn't contains 'lib'
---
<pre>
$ grep -v 'lib' results.txt
</pre>
count all lines which  contains 'lib'
---
<pre>
$ grep  -c 'lib' results.txt
</pre>
Display all lines which  contains 'lib' and proceding with line no.
---
<pre>
$ grep -n 'lib' results.txt
</pre>
Display all lines which dosn't contains 'lib' but only top 5 lines
---
<pre>
$ grep -v 'lib' results.txt | head -5
</pre>

###### Assignment2:

Display all employes data of admin department
---
<pre>
$ grep 'admin' emp.dat
</pre>

Display all employes data of admin and sales department
---
<pre>
$ egrep '(admin|sales)' emp.dat
</pre>

Display all male employes data of admin and sales department
---
<pre>
$ egrep '(admin|sales)' emp.dat | grep -w 'male'
</pre>



##### Type of Regular Expression/Pattren:
All regular expression pattern are devied into 3 types:
1. Character    2. word     3. line

Character pattern:
--
<pre>
$ grep 'd*' demo.txt    ->    It will display all lines which contain d following by any no of character.
In ubuntu these feature is not supporting
</pre>
<pre>
$ grep 'c[aeiou]ll' demo.txt   -> this wil search for matched pattren(like call cill coll etc)
</pre>
<pre>
$ grep 'b..l' demo.txt   -> . means any character. It will search for all four letter where first letter should be b and last letter should be l
</pre>

word pattren:
--
\<word\>    ->    It will display all the lines which contains the specified word. It is exactly same as 
$ grep -w 'word' result.txt     (independent word)
\<xyz    ->    It will display all the word start with xyz.
xyz\>    ->    It will display all the word end with xyz.

line pattren:
---
^   ->    line start with
$   ->    line end with

<pre>
$ grep '^d' demo.txt    ->      the line start with word d.
</pre>
<pre>
$ grep '^the' demo.txt    ->      the line start with word the.
</pre>
<pre>
$ grep '\<the\>' demo.txt    ->      the line start with word 'the' (exactly 'the').
</pre>
<pre>
$ grep '^[aeiou]' demo.txt    ->      the display line start with vowel.
</pre>
<pre>
$ grep '^[^aeiou]' demo.txt    ->      the display line not start with vowel.
here ^(means start with)[^(but if inside like this then it means not)aeiou]
</pre>
<pre>
$ grep 't$' demo.txt    ->      the display line end with word t.
</pre>
<pre>
$ grep '[aeiou]$' demo.txt    ->      the display line end with word vowel.
</pre>
<pre>
$ grep '[0-9]$' demo.txt    ->      the display line end with word digit.
</pre>
<pre>
$ grep '^unix$' demo.txt    ->      It will display all line where total line contains should be unix.
</pre>
<pre>
$ grep '^....$' demo.txt    ->      It will display all line where line contains is exactly 4 character.
</pre>
<pre>
$ grep '^\.' demo.txt    ->      It will display all line start with . symbol
</pre>
<pre>
$ grep '\$$' demo.txt    ->      It will display all line ebd with $ symbol
(here \$ will look for $)
</pre>
<pre>
$ grep '^$' demo.txt    ->      It will display all blank line
</pre>
<pre>
$ grep -v '^$' demo.txt    ->      It will display all blank line
</pre>

How to delete blank line present in the given file.
---
<pre>
$ grep -v '^$' demo.txt > test.txt
$ mv test.txt demo.txt

If we try to do this in one line then we will get following
--
$ grep -v '^$' demo.txt > demo.txt
grep: input file ‘demo.txt’ is also the output
</pre>

###### Advanced pattern supported by egrep but not grep

1. (|)    ->    matches any of the string in the given pattren
2. {m}    ->    matches exactly m no. of proceding character
3. {m,n}  ->    the proceding character should match within m times maximum and n times minimum
4. {m,}  ->    minimum m times but o restriction on maximum

Q1. Write grep command to retrive date values present in the given input fileswhich values are in the form of dd-mm-yyyy or dd/mm/yyyy (like 02-11-1996 or 07/01/1999)
---
<pre>
$ grep -o '\<[0123][0-9][-/][01][0-9][-/][0-9]{4}\>' input.txt
</pre>

Q2. Write grep command to count no. of directories precent in the currunt working directory
---
<pre>
$ ls -l | grep '^d' | wc -l
$ ls -F | grep '/$' | wc -l
</pre>

Q3. Write grep command to count no. of files present in the currunt working directory
---
<pre>
$ ls -l | grep '^-' | wc -l
</pre>

Q4. Write grep command to count no. of link files(@) present in the /etc directory
---
<pre>
$ ls -F /etc | grep '@$' | wc -l
</pre>

Q5. Write grep command to count no. of exicutable files(@) present in the /bin directory
---
<pre>
$ ls -F /bin | grep '*$' | wc -l
</pre>

cut command:
--
we can use cut command to extract data from the file. The file can be either normal file or tabular file.

table 
--
emp.dat
--
eno   |   ename   |   esal    |   eaddress    |   dep   |   gender
100   |   sunny   |   1000    |     mumbai    | admin   |   female
101   |   vinny   |   2000    |     chennai   | sale    |   male
102   |   chinny  |   3000    |     hyderbad  | market  |   male
103   |   bunny   |   2300    |     delhi     | sale    |   male

1.Display character present at specific position in every record:
---
We have to use -c option
-c meant for specific character.
$ cat -c 5 emp.dat    ->    It will display character at 5th position in every row.

2.Display range of character in every record:
--

$ cat -c 5-9 emp.dat    ->    It will display 5th to 9th character in every record.
$ cat -c -4 emp.dat    ->    It will display 1st to 4th character in every record.
$ cat -c 5-9, 16-19 emp.dat    ->    It will display 5th to 9th character and 16th to 19th character in every record.

3.Display specific column data:
--
$ cut -d '|' -f 3 emp.dat   ->    It will display 3rd column data
-d means delimiter (seprator). The default delimiter is tab
-f mean field (column)

4.Disp;ay range of column:
---

$ cut -d '|' -f 2-3 emp.dat   ->    It will display 2nd column to 4th column data.
$ cut -d '|' -f 2- emp.dat    ->    It will display 2nd column to last column data.
$ cut -d '|' -f -3 emp.dat   ->    It will display 1st to 3rd column data.
$ cut -d '|' -f 1,3,5 emp.dat   ->    It will display 1st, 3rd, 5th column data.

5.Skip specific column:
---

Display all column except specific column.
$ cut -d '|' --compliment -f 3 emp.dat   ->    It will display all column data except 3rd column.
$ cut -d '|' --compliment -f 3-5 emp.dat   ->    It will display all column data except 3rd to 5th column
$ cut -d '|' --compliment -f 3- emp.dat   ->    It will display all column data except 3rd to last column
$ cut -d '|' --compliment -f -3 emp.dat   ->    It will display all column data except 1st to 3rd column

paste command:
--

we can use paste command to join 2 or more files horizentaly by using some delimeter, default delimiter is tab.

$ paste file1 file2 file2 ......
eg.
$ paste -d '-' courses.txt fee.txt  =>    two files combines and the delimiter is -
we can specify our own delimiter by using -d
$ paste -d ':' courses.txt fee.txt  =>    two files combines and the delimiter is :
Note:
--
delimiter should be only one character, if we are providing more than one character then only first character consider.

tr command:
--

tr means translate
These command can be used to translate character by character.

$ tr 'aeiou' 'AEIOU' < demo.txt   =>    it will replace every lower case vowel to upper case vowel.

$ tr '[a-z]' '[A-Z]' < demo.txt   =>    it will replace every lower case alphabet to upper case alphabet.

$ tr '[a-zA-Z]' '[A-Za-z]' < demo.txt   =>    it will replace every lower case alphabet to upper case alphabet and every upper case alphabet to lower case alphabet.

$ tr '[a-zA-Z]' '[A-Za-z]' < demo.txt > temp.txt  =>    it will replace every lower case alphabet to upper case alphabet and every upper case alphabet to lower case alphabet and write to temp.txt.

$ tr 'aeiou' '7' < demo.txt   =>    it will replace every lower case vowel with 7

$ tr '|' '\t' < emp.dat   =>    it will replace every | with tab in emp.dat

-d option 
-d means delto    it will delete

$ tr -d 'a' < demo.txt   =>    it will remove 'a' from the demo.txt

$ tr -d 'aeiou' < demo.txt   =>    it will remove every lower case vowel

-s option:
-s means sqeeze repeats
it will change aa aaa  aaaaa aaaaaaaaa ....     to    a

$ tr -s 'a' < demo.txt   =>    it will replace a sequence of 'a' with a

