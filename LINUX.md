# Linux commands for fun ⚙️ 

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
_cp file1,file2 dir <br />
<br />

### mv
Moves files <br />
__moves content from file1 to file1__ <br />
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
❗__YOU HAVE TO BE VERY CAREFULLY WITH THIS DANGEROUS COMMAND!__ 

<br/>

### ps
Display user processes. <br/>
We can use the options below: <br/>

__a__: Display all user, not only about the terminal in use. <br/>
__u__: A detailed exit or _user-oriented_ with much more information. <br/>
__x__: Display all the processes, including those not associated with any terminal, like daemons. <br/>

```terminal
ps aux
```

### grep
Command used as a filter to search keywords to find information. Usually used with pipes (|). <br/>

```terminal
ps aux | grep apache2
```

### spoofing your MAC address

_ifconfig_ is the comand to query your active network connection and active newtwork interfaces. <br/>
To change our MAC address, we could: <br/>

```terminal
ifconfig eth0 down
ifconfig eth0 hw ether 00:11:22:33:44:55
ifconfig eth0 up
```

### examining DNS with dig

```terminal
dig google.com ns
```

_ns_ is for __name server__ <br/>


```terminal
dig nasty-mail-server.com mx
```

_mx_ is for __mail exchange__ <br/>

### installing stuff

Before installing something, maybe we want to know if it is available. <br/>

```terminal
apt-cache search snort
```

Now we can install: <br/>

```terminal
apt-get install packagename
```

Now we can uninstall: <br/>

```terminal
apt-get remove packagename
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

### Create a temporary alias

```terminal
alias aliasname='df . | awk "NR=2" | cut -d " " -f 1'
```

We need the command "alias" + the name of our alias + "=" + the command line in simple quotes. <br/>
To execute the command, just type the alias name. If we close the terminal, this alias is gone. <br/>

### Create an alias

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

### Create a script

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

We gave permissions to the file with: <br/>
```terminal
chmod +x sayHello.sh
```

Then we just run: __./sayHello.sh__ <br/>

### Run any script from anywhere

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

### Terminal tips

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


## TIP for MAC 🍎 
To access a folder in our network, we choose "Go" in the main menu. <br/>
Then "Conect to server" <br/>
Write, for example: "smb:\\172.16.xxx.xxx"<br/>








