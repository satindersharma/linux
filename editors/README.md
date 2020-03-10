### Working with editors:

We can use editors to develp and edit shell programs.

There are multiple editors available.

1. gedit    (most unix/linux flavor have this but not everyone)
2. viedtor   (this is universal editor. it is going to available in every unix based os.)
3. nano editor

#### gedit:
It is a graphical editor. It is simply same as window notepad.

$ gedit first.sh
echo "hel o"
mkdir dir{1..6}
echo "6 dir created"

ctrl+s    ->    to save
ctrl+a    ->    to exit/quit

$ ./first.sh    ->    permission denied

$ chmod u+x first.sh   ->      It will give the exeute permission to the user

Note:
--
gedit is avialable only in GUI based linux flavours like ubuntu. It is not available in remote server. 
By using putty if we are connecting with remote servers we can't use gedit and compalary we should use vieditor

vi editor is UNIX based. gedit, nano editor is Linux based.
vi editor works everywhere.

### vi editor:
vi means visual editor
we can use vi editor to create new files and edit exitsting files.

$ vi second.sh

If second.sh is not available then a new file will be cread and open that file for editing purpose.

To save file we should use   :wq      ( w means save and q means quit)

If file already contains some data then this editor will be opened the file and read for edit.

The 3 modes of vi editor:
---

There are 3 modes are availble while editing file contents.

1.command mode:
--
It is the default mode
Hence we can use vi command

from command mode we can enter into insert mode by using multiple ways , but moslty using i

2.insert mode:
--
In this mode we can insert and edit file content.
from insert mode,we can enter into command mode by using <esc> key    (escape key)
 
3.exit mode:
--
We can use these mode to quit from the editor.
from the command mode , we have to press : then we can enter into exit mode.

vi editor   ->    i   ->    esc   ->    :   ->    w   ->    q

A     ->    To append data at the end of the line.
I     ->    To insert data at the begning of the line.
a     ->    To  append data to the right side of the curser position i.e just after cursor position
I     ->    To  insert data to the left side of the curser position i.e just before cursor position

How to delete data:
--
We can delete data either by character wise or via word wise or via by line wise

delete character wise:
--
x   ->    To delete a single character (del key)    ->    x
3x  ->    To delete 3 character ( insed of 3 we can use any number)
X+  ->    to delete precious character (backspace key)
3X  ->    To delete last 3 precious chacter

deletion words wise:
--
dw  ->    To delete currunt word
3dw  ->   To delete 3 words

deletion line wise:
--
dd  ->    To delete a particular line
3dd ->    To delete 3 lines
d&  ->    To delete from currunt postion to end of line
$d  ->    To delete from begin to currunt cursor postion in the currunt line
dgg ->    To delete from begining of the file to currunt cursor postion line
dG  ->    To delete from currunt postion to end of file

How to replace data:
--
r         ->    replace currunt character
R         ->    to replace multiple character from the currunt postion
S or cc   ->    To repalce currunt line

Opening new line to insert data:
--

O   ->    To open a line above the cursor postion i.e currunt line
o   ->    To open a line below the cursor postion i.e after currunt line

copy and paste data:
--
