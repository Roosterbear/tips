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

### heads and tails

We can see the first lines of a file with: <br/>

```terminal
heads file.txt
```

We can see the last lines of a file with: <br/>

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

## TIP for MAC 🍎 
To access a folder in our network, we choose "Go" in the main menu. <br/>
Then "Conect to server" <br/>
Write, for example: "smb:\\172.16.xxx.xxx"<br/>








