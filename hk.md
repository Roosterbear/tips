# I am the 👁️  in the sky 🔓

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

* For bundle file, CHANGE PERMISSIONS, and run it with __sudo ./VMWare__...

_Uninstall VMWare Workstartion Player and Pro_:

>sudo vmware-installer -u vmware-player
>sudo vmware-installer -u vmware-workstation

__Configuring the Network__<br/>

#### Bridged Network

* Connects the VM directly to the local network, it is another node with its own IP address.

#### NAT (Network Address Translation)

* Sets up a _private_ network on the host machine, all the traffic appear to come from the host machine's IP address. 

#### Host only network

* The VM will be able to communicate with other Virtual Machines.  
* It will not be able to connect with internet or the local network. 


## LABS

* Only VMs for the Labs (Attacker and Targets)
* Preferably Use VMWare
* Use an external SSD drive to mount your Labs
* All VMs will be interconnected and isolated from any other external network
* VMWare allows us to create a virtual network without the need for a router or switch. 
* Each virtual machine should obtain an IP address through DHCP. 
* The DHCP server will be managed internally by VMWare



### Preparing Attaker VM

* Download a Kali Linux for VMWare
* Once you have installed VMware Workstation Player/Pro
* Unzip the Kali Linux (.7z) and open the .vmx file from VMware.
* Adjust Network Adapter to NAT
* Adjust your resources (like RAM and Processor)
* VMware will ask you whether you moved or copied the virtual machine
* Choose 'I Copied It' to proceed
* Start session with kali/kali
* CHANGE pasword from terminal with: passwd
* Update Kali:
>sudo apt update && sudo apt dist-upgrade -y
* Install open-vm-tools for VMWare in a terminal of Kali and type:
>sudo apt-get install open-vm-tools-desktop fuse3
* Restart:
>sudo reboot


### Preparing Targets Metasploitables

* Like the Attaker VM, install Metasploitable1 (Windows Server 2008) Target (vagrant/vagrant)
* Open as Administrator a CMD window and type:
>slmgr /rearm
* Reboot the VM from the command line with:
>shutdown -r -t 0
* Now the desktop will be clean and no messages from activations will appear
* with VMWare Pro, shutdown the Metaspolitable and save a snapshot
* In the Windows 10 VM, use the same configuration as the last one (Users/Passw0rd!)
* Install the Metasploitable2 (msfadmin/msfadmin)


## BASICS

* We can use variables. To load a variable, use:
>echo $PATH
_Where PATH is the variable and we load it with the $ sign_ <br/>

* We can create our variables:
>myvariable=100
>echo $myVariable
_Do not type spaces between the equal sign_ <br/>

* To see our Environment Variables we use:
>env

* To see all variables we use:
>set

* Commands to check our variable:
>set | grep myVariable
>env | grep myVariable

* To convert a local variable to environment variable, use:
>export myvariable

* To delete a variable, we type:
>unset myVariable

* We can use an alias temporaly:
>alias ll='ls -al'

* If we want the Alias to be persistent, we can modify de __~/.zshrc__ file:
>source ~/.zshrc

* To show ALL Aliases, just:
>alias

* to delete an Alias, type:
>unalias myAlias


## SYSTEM ENUMERATION

__"It is when we search for system information to better understand the machine we are attacking."__ <br/>
>uname -a
>cat /etc/issue


### LS

__"List files and directories"__ <br/>

* Including hidden files:
>ls -a

* Including details:
>ls -l

* Including the content of directories:
>ls -lR


### TOUCH

__"Creates a new file"__ <br/>
>touch newfile.txt

* If it was created yet, the command modifies the __access__ and __modified__ _timestamp_ <br/>
* Modify just the __access__ timestamp:
>touch newfile.txt -a
>stat newfile

* Modify just the __modified__ timpestamp:
>touch newfile.txt -m
>stat newfile

* __CHANGE__ the date of timestamp:
>touch -d newfile.txt "2023-11-16 08:33:51"
>stat newfile

* Use the timestamp of a file as __reference__ to other file
>touch -r ejemplo.py ejemplo2.py


### RM

__"Deletes a file or directory"__ <br/>

* Deletes a directory, including its contents:
>rm -r mydirectory

* Deletes a file or directory even though it has read-only permissions without prompts:
>rm -f myfile


### MANIPULATING FILES

* Copy a file
>cp file /directory

* Move a file
>mv file /directory

* Rename a file
>mv file newname

* Create a soft link
>ln -s sourcefile.txt /tmp/mylink.txt
_Is like a direct access icon_ <br/>
_If the source file is deleted, the link get useless and throws an error_ <br/>

* Create a hard link
>ln sourcefile.txt /tmp/mirror.txt
_Is like a mirror file_ <br/>
_If the source file is deleted, the link is a backup still working_ <br/>

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


## REDIRECTION AND PIPING

* There are 3 flows we can _redirect_: __INPUT__, __OUTPUT__ and __ERROR__
* We can use the output character: __>__ to redirect de output to another
* To get the _ERRROR_ output, use __2>__
>ls -al doesnotexist.txt 2> myerror.txt
* To count words, we can use _wc -m_ and the input character: __<__
>wc -m < file.txt
* To piping, use __|__ and send the output to a command
>ls | wc -l


### grep

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

### sed

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



## USERS

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


## PERMISSIONS

>levels
* __u__ user
* __g__ group
* __o__ other

>access
* __r__ read
* __w__ write
* __x__ execute

>files
* __read__ copy or read a text file
* __write__ change the file
* __execute__ open a binary file / execute a script

>directories
* __read__ list the inner files
* __write__ delete the directory
* __execute__ enter the folder or directory

__There are 2 ways to change permissions: symbolic and numerical (_octal_)__ <br/>

### symbolic
>chomod u=rwx,g+rw,o-r file.txt

* __a__ means "ALL"
>chomod a=rx file.txt

### numeric
>chmod 777 file.txt

* __7__ is the maximum permissions to give (_read - write - execute_)
* The order is: _user, group, other_
* __4__ is for _READ_ 
* __2__ is for _WRITE_
* __1__ is for _EXECUTE_

>chmod 754 file.txt
* _read - write - execute_ permissions for the owner
* _read - execute_ permissions for the group
* _read_ permissions for others

### chown

* Changes the owner
>chown root file.txt

### suid _(set user ID)_
* Allow current user exec the file with the _OWNER_ rights
>chmod u+s file
* Now you can see the permission with _ls -l_

* Delete SUID
>chmod u-s file

### sgid _(set group ID)_
* Allow current user exec the file with the _GROUP_ rights
>chmod g+s file
* Now you can see the permission with _ls -l_

* Delete SUID
>chmod g-s file

### sticky bit
* For directories
* Restricts the deletion of files
* Only their owner or the owner of the parent directory can delete the file
>chmod +t directory



























## PENTESTING PHASES

* __Engagement__ with the client. 

* __Reconnaissance__ the information gathering

* __Vulnerability Explotation__ identifying vulnerabilities in a system

* __Explotation__ test and attack the target

* __Clean-up__ delete files, exploits or accounts used in the pentesting

* __Report__ Recommendations and potential fixes for discovered information


### Reconnaissance

* __Pasive footprinting__ or __OSINT__ Open Source Intelligence
>Involves gathering information about the target without their awareness
>All the information we can get from outside, by public sources:
* WHOIS Databases
* Search Engines
* Social Networks
* Web Pages
* Job postings that need to inform the vacancy requirements
* Geo-Labeled pictures 
<br/>

* __Data to get:__
>Networking:
* Domains
* Net segments
* IP direction
* DNS Servers

>Systems:
* Operative Systems
* Web Technologies
* Location

>Organization
* Names
* Phone numbers
* E-mails
* News


## PROTECTION AND ANONYMITY

* Assessing your anonymity while browsing the Internet:

>https://coveryourtracks.eff.org/
>https://browserleaks.com/

* Virtual Machine __Trace Labs OSINT__ to researches:

>https://www.tracelabs.org/initiatives/osint-vm

* Extensions for browsers:
>Ublock Origin
>Privacy Badger
>User-Agent Switcher and Manager

## SEARCH TIPS

* site
>site: domain.com something

* intitle
>intitle: something interesting

* inurl
>inurl: hacking

* link
>link: mywebsite.com

* type
>mysearch .pdf
>mysearch type:pdf
>mysearch ext:pdf

* Exploit Database: 
>https://www.exploit-db.com/google-hacking-database/

















# 👁️👁️  

## Nessus

* Register on: http://www.tenable.com/products/nessus-home/ <br/>
* Open a __root__ terminal and go to Download folder <br/>
* __dpkg -i__ and add the file name <br/>

>You can start Nessus Scanner by typing /bin/systemctl start nessusd.service
>Then go to https://kali:8834/ to configure your scanner


