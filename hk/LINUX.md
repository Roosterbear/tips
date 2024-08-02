# LINUX ===============================================================

## MOVING ON LINUX

### ls -----------------------------------------------------------------

Lists the content of the current directory <br />
-a including hidden files <br />
-l Whole data of every files (date, permissions, owner, group) <br />
-r Reverse order <br />
<br />

### cp -----------------------------------------------------------------

Copies files
__copy content from file1 to file2__ <br /> 
_cp file1 file2_ <br />
__copy files to directory dir__ <br />
_cp file1,file2 dir_ <br />
<br />

### mv -----------------------------------------------------------------

Moves files <br />
__moves content from file1 to file2__ <br />
_mv file1 file2_ <br />
__moves files to directory dir__ <br />
_mv file1, file2 dir_ <br />
<br />

### touch --------------------------------------------------------------

Creates a new file or updates the timestamp of that file <br />
_touch file_ <br />
<br />

### cat ----------------------------------------------------------------

We can create a __new__ file with: <br/>

```terminal
cat > file.txt
```
If we run that command again, the information will be replaced with the new one. <br/>

We can __see__ the _content_ of a file with: <br/>

```terminal
cat file.txt
```

We can add data with: <br/>

```terminal
cat >> file.txt
```

### head and tail ------------------------------------------------------

We can see the first __10__ lines of a file with: <br/>

```terminal
heads file.txt
```

We can see the last __10__ lines of a file with: <br/>

```terminal
tails file.txt
```

### nl -----------------------------------------------------------------

We can number the rows by:

```terminal
nl /etc/snort/snort.conf
```

### path expansion -----------------------------------------------------

We can open, list or name a file with characters like a dash with path expansion. <br/>
If I have a folder named "---old---", I just can change the directory this way: <br/>

```terminal
cd -- ---old---
```

The __path expansion__ uses double dash between the comand and the name of the file / directory. <br/>


### mkdir --------------------------------------------------------------

Creates a new directory <br />
_mkdir dire_ <br />
<br />


### rmdir --------------------------------------------------------------

Deletes an empty directory <br />
_rmdir dire_ <br />


### rm -----------------------------------------------------------------

Deletes a file or definitely <br />
rm file1 <br />
-r _recursively_ <br />
-f _force_ <br />


### Deletes a directory with other files or directories ----------------

rm -rf important <br />
__YOU HAVE TO BE VERY CAREFULLY WITH THIS DANGEROUS COMMAND__ ❗ <br/>

<br/>


### Delete all PNG files -----------------------------------------------

```terminal
rm *.png
```


### Delete all files, except... ----------------------------------------

```terminal
rm !(*.html)
```
Delete all files except _.html_ files. <br/>


### Status error last command ------------------------------------------

```terminal
$?
```

### Access USB ---------------------------------------------------------

We can see them in: <br/>

```bash
cd /media/user
```

or <br/>

```bash
cd /mnt/user
```



## FILES

### Tarring ------------------------------------------------------------

We can compress lossy (_.mp3, .flac, .mp4, .png, .jpg_) and lossless ( _.tar, .zip, .rar_). <br/>

To compress, we can tar them, it means, grouping them in a file. <br/>

```bash
tar -cvf MyCompressions.tar file1.txt file2.txt
```

Let's analyze the __-cvf__ parameters: <br/>

* __c__ create
* __v__ verbose
* __f__ the following file

See files in a __.jar__ file: <br/>

```bash
tar -tvf MyCompressions.tar
```

Extract files from a __.tar__file: <br/>

```bash
tar -xvf MyCompressions.tar
```

### Compressing --------------------------------------------------------

* __gzip__ with extension _.tar.gz_ or _.tgz_ FASTER <br/>
* __bzip2__ with extension _.tar.bz2_ SLOWEST - SMALLEST <br/>


__gzip__

Compress: <br/>

```bash
gzip MyCompressions.tar
```
__NOTICE__ that MyCompressions.tar was replaced by _MyCompressions.tar.gz_ !!!

Uncompress: <br/>

```bash
gunzip MyCompressions.tar.gz
```
__NOTICE__ _MyCompressions.tar_ is back and _MyCompressions.tar.gz_ is gone !!!


__bzip2__ <br/>

Compress: <br/>

```bash
bzip2 MyCompressions.tar
```

Uncompress: <br/>

```bash
bunzip2 MyCompressions.tar.bz2
```

## PERMISSIONS 

### Intro -------------------------------------------------------------

We have 3 kind of permissions: <br/>

READ _r_ <br/>
WRITE _w_ <br/>
EXECUTE _x_ <br/>


We have 3 groups: <br/>

USER _u_ <br/>
GROUP _g_ <br/>
OTHER _o_ <br/>


__EXAMPLES__ <br/>

>chmod o-x file1
>chmod g+r file1
>chmod +w file1
>chmod go-w file1

<br/>

>sudo chmod ugo +rwx -R folder3

* Where -R is _recursive_ <br/>


__change owner permissions__ <br/>

>chown lf file3


__add a user to a group__ <br/>

>add user lf vboxusers

* Where lf is a _user_ and vboxusers is a _group_ <br/>

__create a user__ <br/>

>useradd lf

__generate a password for a user__ <br/>

>passwd lf

* Where lf is the user to give a _password_ <br/>


__remove the read permissions__

```terminal
chmod -r thefile.txt
```

__remove write permissions__

```terminal
chmod -w thefile.txt
```

__add permissions__

```terminal
chmod +rw thefile.txt
```

__change owners__

```terminal
chown bob /tmp/bobsfile
```

__change group__

```terminal
chgrp security newIDs
```

## Users --------------------------------------------------------------

* Lock user
>sudo usermod -L theuser

* Unlock user
>sudo usermod -U theuser

* User Configuration
>sudo chage -l theuser

* Expire user
>sudo chage -E 2001-01-01 theuser

* Show current user Groups
>groups

* Session as root
>sudo -i
>su

* Change user
>su theuser



## PROCESS 

### ps ----------------------------------------------------------------

Display user processes. <br/>
We can use the options below: <br/>

__a__: Display all user, not only about the terminal in use. <br/>
__u__: A detailed exit or _user-oriented_ with much more information. <br/>
__x__: Display all the processes, including those not associated with any terminal, like daemons. <br/>

```terminal
ps aux
```

<br/>
__actual process id:__ $$ <br/>
__process folder:__ cd /proc <br/>
__folder to actual process:__ cd $$ <br/>
__executable of current task:__ ls -l exe <br/>
<br/>

### lsof ---------------------------------------------------------------

Give us detailed information about files used in current processes. <br/>
Normally requires Admin privileges. <br/>

__We can list files that are listening TCP connections by:__ <br/>

```terminal
sudo lsof -iTCP -sTCP:LISTEN -n -P
```

__List open files by a number of proccess (123)__ <br/>

```terminal
sudo lsof -p 123
```

__Opened files by a user__ <br/>

```terminal
sudo lsof -u usuario1
```

__Search active connections__ <br/>

```terminal
sudo lsof -i -P -n | grep LISTEN
```

### Redirect output to a file ------------------------------------------

__Creating__ <br/>

```terminal
ls / > list_of_root.txt
```
__Adding__ <br/>

```terminal
sudo lsof -i -P -n | grep LISTEN
```


### top ----------------------------------------------------------------

Lists the processes running in the system. <br/>

<br/>

_shift+m_ orders by memory use.
_shift+p_ orders by CPU use.
_shift+n_ orders by process.

### htop ---------------------------------------------------------------

A better version of __top__ which we can easily install. <br/>

__free__

We can see the use of memmory of the system. It is better with _-h_ (for Humans) <br/>

### grep ---------------------------------------------------------------

Command used as a filter to search keywords to find information. Usually used with __pipes__ (|). <br/>

Its name is from g/re/p __Globally__ Regular Expression __Print__ <br/>

<br/>

__Literally__ <br/>

We can use -F option or fgrep to ask for literal results as: <br/>

>echo 'int a[5]' | grep -F 'a[5]'
>echo 'int a[5]' | fgrep 'a[5]'

<br/>

__Case 'Insensitive' search__ <br/>

>grep -i 'jam' quotes.txt
_use regular expressions. Now they have two problems by Jamie Zawinski_ <br/>

<br/>

__Invert search__ <br/>

>seq 5 | grep -v '3'
1 <br/>
2 <br/>
4 <br/>
5 <br/>

<br/>


__find lines with a text__ <br/>

```terminal
grep file file.txt
```

Where __file__ is the _word to find_ and __file.txt__ is the _file_ where it has to look. <br/>

__find lines with a text and the line number__ <br/>

```terminal
grep file file.txt -n
```
We can use _-c_ to count the lines. <br/>
We can use _-w_ to look only separate words. <br/>

* Used to search patterns, most of the time, pipes the STDOUT to get data
>grep "word" file.txt

__Regex__ <br/>

* __^__ Matches with the beginning of the line
* __$__ Matches with the end of the line
* __.__ Matches with ONE (any) character
* __*__ Matches with 0 - N characters
* __[]__ Matches with characters inside (a list[abc] or range[a-z])
* __[^]__ Matches with non of the characters inside (a list[abc] or range[a-z])
* __\+__ Matches one or more preceding character and only one of the next character
>cat file.txt | grep "a+b" __look for exact characters__
>cat file.txt | grep "a\+b" __look for any number of "a" with a "b" next to it
* __\?__ Matches zero or one preceding character and one or more next character
>cat file.txt | grep "a\?b" __look for any number of "b" and zero or one "a" before


### pipes --------------------------------------------------------------

* There are 3 flows we can _redirect_: __INPUT__, __OUTPUT__ and __ERROR__
* We can use the output character: __>__ to redirect de output to another
* To get the _ERRROR_ output, use __2>__
>ls -al doesnotexist.txt 2> myerror.txt
* To count words, we can use _wc -m_ and the input character: __<__
>wc -m < file.txt
* To piping, use __|__ and send the output to a command
>ls | wc -l


Sends the output of a command to another command. <br/>

__list the current folder, only the first 20 lines and withe the word "root" in it.__ <br/>

```terminal
ls -al | head -20 | grep root
```

__find all process with the word apache2__

```terminal
ps aux | grep apache2
```

__find line numbers where is a text__ <br/>

```terminal
grep file file.txt -n | cut -d ":" -f 1
```

Where __-n__ says the number of line <br/>
Then we cut the rest, since we get the line, colon and the search. <br/>



### sed (Stream EDitor) ------------------------------------------------

We can replace text: <br/>

```terminal
echo "hello there" | sed 's/there/here/'
```


We can delete lines: <br/>

```terminal
sed '/pattern/d' file.txt 
```


We can delete lines: <br/>

```terminal
sed '/pattern/d' file.txt 
```

* Replace text
>sed 's/+/_/' file.txt
* __s__ replace
* Replace + by _
* Check that has to en with "/"
* Replace just the first character found

>sed 's/a/z/g' file.txt
* Replace all characters found

### cut

* Gets text from a line
* __-f__ selects field
* __-d__ selects delimiter (_JUST ONE CHARACTER_)
>echo "blackberries, figs, mammees" | cut -f 2 -d ","




### awk

* Process data like cut, but can use _MORE_ than ONE character as delimiter
>echo "Hola:::mundo:::como:::estas" | awk -F ":::" ' {print $1, $2}'





## LOGS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

We can find them in: <br/>
>/var/log

## systemctl ----------------------------------------------------------

__Status__ <br/>

```terminal
sudo systemctl status apache
```

__Enable service__ <br/>

```terminal
sudo systemctl enable apache
```

__status__ <br/>

```terminal
sudo systemctl status apache
```

__disk used for logs__ <br/>

```terminal
sudo systemctl --disk-usage
```

__times system was reboot__ <br/>

```terminal
sudo systemctl --list-boots
```

__info by level__ <br/>

```terminal
sudo systemctl -p crit
sudo systemctl -p err
sudo systemctl -p info
```


## INSTALLING @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

Before installing something, maybe we want to know if it is available. <br/>

```terminal
apt-cache search snort
```

Now we can install: <br/>

```terminal
apt-get install [packagename]
```

We can uninstall: <br/>

```terminal
apt-get remove [packagename]
```

To check if there are updates in the lists of repositories we can type: <br/>

```terminal
apt-get update
```

If so, the updates are downloaded. <br/>

To __upgrade__ to a new version our installed packages, we can use: <br/>

```terminal
apt-get upgrade
```

__Knowing the console we are working with__ <br/>

Just type: <br/>

```terminal
echo $SHELL
```

__show gateways__ <br/>

>route -n


## SCRIPTS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

We can edit a new file with vi: <br/>

```terminal
vi sayHello.sh
```

Now we must write: __#!/bin/bash__ <br/>
Then we can add any command, like: 

```terminal
echo "Hello world"
```

Save our file with __:wq__ <br/>

We give _execute_ permissions to the file with: <br/>
```terminal
chmod +x sayHello.sh
```

Then we just run: __./sayHello.sh__ <br/>

* We can create our variables:
>myvariable=100
>echo $myVariable
_Do not type spaces between the equal sign_ <br/>


## Run any script from anywhere ---------------------------------------

Check: <br/>

```terminal
echo $PATH
```

The first line before ":" tell us the path where we have to copy our script:

```terminal
vi hola
```

Add: <br/>

```terminal
#!/bin/bash
echo "Hola "$@
```

And then: <br/>
```terminal
chmod +x hola
cp hola /home/lf/.local/bin/
```

__Now we can run:__

```terminal
hola Fernando
```

__A script to change a sentence from lowercase to uppercase__

```bash
#!/bin/bash

echo $@ | tr 'a-z' 'A-Z'
```

or <br/>

```bash
#!/bin/bash

echo $@ | tr '[:lower]' '[:upper]' 
```

## Save the path of a directory ---------------------------------------

```terminal
pushd .
```

Now we can change the directory and get back with: <br/>

```terminal
popd
```

## history ------------------------------------------------------------

To show all commands we typed, we use: _history_ <br/>

To delete a line of history we type: _history -d xxxx_ <br/>
Where _xxxx_ is the number of the command.

__avoiding to register a command in history__ <br/>
 We just have to let a blank space before the command. 👌🏾 <br/>

__number of lines of history__ <br/>

```terminal
echo $HISTSIZE
```

__knowing the default editor__ <br/>

```terminal
echo $EDITOR
```

__modify and run the last command__ <br/>

```terminal
fc
```
We just modify the line and the command will be executed. <br/>

---
---
---


#### Find

__files__ <br/>

```terminal
find . -type f -iname *.py
```
. from current directory <br/>
__f__ files <br/>
_iname_ it dowsn't matter if it's uppercase or lowercase. <br/>
That contains the _py_ extension. <br/>

__directories__ <br/>

```terminal
find ~ -type d -iname *python*
```

~ from home directory <br/>
__d__ directories <br/>
_iname_ it doesn't matter if it's uppercase or lowercase. <br/>
That contains the word _python_ <br/>


* Wildcards
>ls -l sys*
_files starting with "sys"_ <br/>

>ls -l sys[1-5]*
_files starting with "sys" and a number between 1 and 5_ <br/>

>ls -l file??.txt
_files starting with "file", then 2 characters and TXT type_ <br/>

* Seek files
>which nmap
>whereis nmap

__locate__ <br/>
>locate mimikatz.exe
_this command uses locate.db and updates its data eventually_ <br/>
_to update locate DB:_ <br/>
>sudo updatedb

__find__ <br/>
>find / -name text.txt
_finds from root the file text.txt_ <br/>
>find . -type f -name "*.jpg"
_finds from current directory, all JPG files_ <br/>
>find /etc -user kali -size 1M -type f -name "*.txt" 
_finds from etc directory, TXT files larger than 1Mb from the kali user_ <br/>
>find /home -type d -iname "user"
_finds all DIRECTORIES with the name "user" with NO CASE SENSITIVE_ <br/>



#### tar

Stands for "tape archive" and is used to combine files into one archive. <br/>

__combine files__ <br/>

```terminal
tar -cvf texts.tar text1 text2 text3
```

__display files__ <br/>

```terminal
tar -tvf texts.tar
```

__extract files__ <br/>

```terminal
tar -xf texts.tar
```

Where __c__ is for create, __v__ is for _verbose_ and __f__ is for write the _following file_ <br/>

#### compress

__bzip2__ with extension _.tar.bz2_ is the slowest but generates the __smallest__ files.
__compress__ with extension _.tar.z_ is the fastest but generates the __biggest__ files.
__gzip__ with extension _.tar.gz2_ or _.tgz_ falls somewhere in between.

<br/>
---
---
<br/>

## Knowing DATA 🐍 

```terminal
stat file.txt
```

__knowing data from the system__ <br/>
```terminal
stat /
```

__translate__ <br/>
```terminal
sudo apt-get install translate-shell
```

Now, translate a file: <br/>
```terminal
cat file.txt | trans
```

__know my processor__ <br/>

```terminal
cat /proc/cpuinfo | grep "model name" | head -n 1
```

__know the memory__ <br/>

```terminal
cat /proc/meminfo 
```

__know the disc free space__ <br/>

```terminal
df -h .
```

__know the kernel__ <br/>

```terminal
cat /proc/version
cat /proc/version | cut -d " " -f 3
```

Where cut separates the sentence by spaces and takes the third. 🪚 <br/>

__know the groups of the current user__ <br/>

```terminal
groups
```

__know how much time the computer is on__ <br/>

```terminal
uptime
```

__list the USB devices__ <br/>

```terminal
lsusb
```

__list wifi networks__ <br/>

```terminal
nmcli dev wifi
```

__deactivate wifi__ <br/>

```terminal
nmcli radio wifi off
```

__activate wifi__ <br/>

```terminal
nmcli radio wifi on
```

__install ifconfig__ <br/>

We need _net tools_ that includes that command.<br/>

```terminal
sudo apt install net-tools
```

__know only the IP of the computer__ <br/>

```terminal
hostname -I
```

__information about an image__ <br/>

```terminal
identify imagen.png
```

__list files from previous folder__ <br/>

>ls ../

__list processes__ <br/>

>ps -axf

__hard disk used__ <br/>

>du

__hard disk left__ <br/>

>df

__groups where I am in__ <br/>

>groups


__read NEWS without suscription__ <br/>

```terminal
lynx https://www.periodico.com/noticias/2022-05-08/forbidden_news.html
```

__open an image from terminal__ <br/>

>eog photo.jpg

__generate QR Codes__ <br/>

```terminal
sudo apt-get install qrencode
qrencode "hola mundo" -o codigoqr.png
display codigoqr.png
```

__read QR Codes__ <br/>

```terminal
sudo apt-get install zbar-tools
zbarimg codigoqr.png
```

__read OCR, text from images__ <br/>

```terminal
sudo npm install -g imgclip
imgclip holamundo.jpg
```

__create a colored canvas__ <br/>

```terminal
convert -size 800x400 xc:black black_canvas.png
```

__create a colored canvas with a text__ <br/>

```terminal
convert -size 800x400 background WhiteSmoke -font Arial-bold -pointsize 45 -gravity Center label: "Hola" cartel.png
```

__create a sign from words__ <br/>

```terminal
sudo apt install figlet
figlet hola mundo
```

__create a sign with animals__ <br/>

By default is a cow: '_cowsay hola_' <br/>
But we can change them. We can see all the available animals with: '_cowsay -l_' <br/>

```terminal
cowsay -f animal mensaje
```

__create text wrapped in boxes__ <br/>

```terminal
echo mensaje | boxes
```

We can see all the available boxes with: '_boxes -l_' and change it with:<br/>

```terminal
echo mensaje | boxes -d stone
```
__change console:__ sh - bash - zsh <br/>



__math operations__

```terminal
echo 3+2 | bc
expr 3 + 2
echo $((3+2))
```



## COMPARATING FILES

### comm

* Compares 2 files
* Show lines exclusive in file 1
* Show lines exclusive in file 2
* Show lines shared in both files
* __Flag__ _-n_ can remove 1st, 2nd or 3rd
>comm -12 file1.txt file2.txt


### diff

* shows differences between files
* Standard format:
> diff file1.txt file2.txt
* Unified format:
> diff -u file1.txt file2.txt
* Recursive files in directories:
>diff -r directory1 directory2


## COMMAND LISTS

### ;
* Separates commands
>echo "Mi user is";whoami

### &&
* Chain commands
* Stops with the first failed command
* Controls the execution of the second command __IF__ the first throws and exit code > 0
>grep "aa" file.txt && rm file.txt

### ||
* Chains commands
* Stops with the first successful command
>grep "zz" file.txt && rm file.txt



## Soft and Hard Links

* Create a soft link
>ln -s sourcefile.txt /tmp/mylink.txt
_Is like a direct access icon_ <br/>
_If the source file is deleted, the link get useless and throws an error_ <br/>

* Create a hard link
>ln sourcefile.txt /tmp/mirror.txt
_Is like a mirror file_ <br/>
_If the source file is deleted, the link is a backup still working_ <br/>



---
---

## ---BASH---

>#!usr/bin/env bash

### We must not let blank spaces between equal sign
>world="world"

### %s is for a string variable
### remember to add a $ to PRINT or CALL variables
>printf "Hello %s$world\n"












