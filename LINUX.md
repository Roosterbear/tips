# LINUX

## Linux commands for fun ⚙️ 

### ls
Lists the content of the current directory <br />
-a _including hidden files_ <br />
-l _Whole data of every files (date, permissions, owner, group)_ <br />
-r _Reverse order_ <br />
<br />

### cp
Copies files
__copy content from file1 to file2__ <br /> 
_cp file1 file2_ <br />
__copy files to directory dir__ <br />
_cp file1,file2 dir_ <br />
<br />

### mv
Moves files <br />
__moves content from file1 to file2__ <br />
_mv file1 file2_ <br />
__moves files to directory dir__ <br />
_mv file1, file2 dir_ <br />
<br />

### touch
Creates a new file or updates the timestamp of that file <br />
_touch file_ <br />
<br />

### cat

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

### head and tail

We can see the first __10__ lines of a file with: <br/>

```terminal
heads file.txt
```

We can see the last __10__ lines of a file with: <br/>

```terminal
tails file.txt
```

### path expansion ♨️ 

We can open, list or name a file with characters like a dash with path expansion. <br/>
If I have a folder named "---old---", I just can change the directory this way: <br/>

```terminal
cd -- ---old---
```

The __path expansion__ uses double dash between the comand and the name of the file / directory. <br/>

### mkdir
Creates a new directory <br />
_mkdir dire_ <br />
<br />

### rmdir
Deletes an empty directory <br />
_rmdir dire_ <br />

### rm
Deletes a file or definitely <br />
rm file1 <br />
-r _recursively_ <br />
-f _force_ <br />

__Deletes a directory with other files or directories__ <br />
rm -rf important <br />
__YOU HAVE TO BE VERY CAREFULLY WITH THIS DANGEROUS COMMAND__ ❗

<br/>

__create a folder with the current date in the name__

```terminal
mkdir "$(date+"%Y-%m-%d")"
```

---

## PERMISSIONS

We have 3 kind of permissions: <br/>

READ <br/>
WRITE <br/>
EXECUTE <br/>

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

---

## Process in Linux

### ps
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

__lsof__ _list open files_ <br/>

Give us detailed information about files used in current processes. <br/>
Normally requires Admin privileges. <br/>

__We can list files that are listening TCP connections by:__ <br/>

```terminal
sudo lsof -iTCP -sTCP:LISTEN -n -P
```
__top__

Lists the processes running in the system. <br/>

<br/>

_shift+m_ orders by memory use.
_shift+p_ orders by CPU use.
_shift+n_ orders by process.

__htop__

A better version of __top__ which we can easily install. <br/>

__free__

We can see the use of memmory of the system. It is better with _-h_ (for Humans) <br/>

## grep
Command used as a filter to search keywords to find information. Usually used with __pipes__ (|). <br/>


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

## pipes |

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

---

#### installing stuff

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

#### Create a temporary alias

```terminal
alias aliasname='df . | awk "NR=2" | cut -d " " -f 1'
```

We need the command "alias" + the name of our alias + "=" + the command line in simple quotes. <br/>
To execute the command, just type the alias name. If we close the terminal, this alias is gone. <br/>

#### Create an alias

```terminal
vi ~/.bashrc
```

We look for alias. There we can see if the ~/.bash_aliases file exists.<br/>
In that file, we can load all the alias we need the same way than temporary alias. <br/>

We need the command "alias" + the name of our alias + "=" + the command line in simple quotes. <br/>
__We need to restart the terminal or write:__ <br/>

```terminal
. ~/.bash_aliases
```

To execute the command, just type the alias name. <br/>

__Knowing the console we are working with__ <br/>

Just type: <br/>

```terminal
echo $SHELL
```

#### Create a script

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

#### Run any script from anywhere

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

---
---

## Terminal tips

__The TAB key help us to complete commands__ <br/>
<br/>

__ctrl+a__ <br/>
Go to the beginning of the line. <br/>

__ctrl+e__ <br/>
Go to the end of the line. <br/>

---

__alt+b__ <br/>
Jump to the last command in the line. <br/>

__alt+f__ <br/>
Jump to the next command in the line. <br/>

---

__ctrl+u__ <br/>
Deletes from cursor to the beginning of the line. <br/>

__ctrl+k__ <br/>
Deletes from cursor to the end of the line. <br/>

__ctrl+w__ <br/>
Deletes the word (_every space separates a word_) before the cursor in the line. <br/>

__alt+d__ <br/>
Deletes the word (_every space separates a word_) after the cursor in the line. <br/>

---

__ctrl+l__ <br/>
Clears the terminal without deleting the __current line__. <br/>

__ctrl+d__ <br/>
Deletes the character after cursor or close the terminal if there is nothing 

__ctrl+t__
Exchange the characters with each other.

---

__ctrl+alt+t__ <br/>
Opens a new terminal. <br/>

__add the output of a command to a file__ <br/>

```terminal
ls > file.txt
```

__add the output of a command to a file without deleting the last information__ <br/>

```terminal
ls >> file.txt
```

__delete the content of a file__ <br/>

```terminal
cat dev/null > file.txt
```

#### save the path of a directory

```terminal
pushd .
```

Now we can change the directory and get back with: <br/>

```terminal
popd
```

#### history

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
_iname_ it dowsn't matter if it's uppercase or lowercase. <br/>
That contains the word _python_ <br/>

#### rm

__delete all PNG files__

```terminal
rm *.png
```

__delete all files, except...__
```terminal
rm !(*.html)
```
Delete all files except _.html_ files. <br/>


__math operations__

```terminal
echo 3+2 | bc
expr 3 + 2
echo $((3+2))
```

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

__read NEWS without suscription__ <br/>

```terminal
lynx https://www.periodico.com/noticias/2022-05-08/forbidden_news.html
```

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

---

### The Terminal

__change console:__ sh - bash - zsh <br/>
_we got to have zsh installed_ <br/>
__install oh my zsh plugin:__ sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" <br/>
__install Powerlevel10k:__ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k <br/>
__install emacs__ <br/>
```terminal
sudo apt-get update
sudo apt-get install emacs 
```
Options - Customize Emacs - Custom Themes - Wombat

__config .zshrc__ In home folder <br/>
__ZSH_THEME__="powerlevel10k/powerlevel10k" <br/>
<br/>

__CLOSE TERMINAL__ <br/>
<br/>

__CONFIG TERMINAL WITH POWER LEVEL 10k__ <br/>
<br/>

__config .p10k.zsh__ In home folder <br/>
1.- Comment all with _alt+x_ in __typeset__ -g POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS <br/>
Keep _ip_ and _status_ <br/>
2.- Just keep __os_icon__ and __dir__  in __typeset__ -g POWERLEVEL9K_LEFT_PROMPT_ELEMENTS <br/>

__install zsh plugins from github for oh my zsh__ <br/>
Install _zsh-autosuggestions_ and _zsh-syntax-highlighting_ <br/>
Add to __.zshrc__ in plugins the plugins above. (Juste leave a __space__ between each plugin)<br/>

__config terminal__ <br/>

file - preferences - shortcuts <br/>

Check: __split terminal__, __collapse subterminal__, __right subterminal__ and __left subterminal__ <br/>


## Emacs

__exit__ Ctrl+x Ctrl+c

---
---

## TIP for MAC 🍎 
To access a folder in our network, we choose "Go" in the main menu. <br/>
Then "Conect to server" <br/>
Write, for example: "smb:\\172.16.xxx.xxx"<br/>








