# I am the 👁️  in the sky 🔓

__Configuring the Network__<br/>

#### Bridged Network

* Connects the VM directly to the local network, it is another node with its own IP address.

#### NAT (Network Address Translation)

* Sets up a _private_ network on the host machine, all the traffic appear to come from the host machine's IP address. 

#### Host only network

* The VM will be able to communicate with other Virtual Machines.  
* It will not be able to connect with internet or the local network. 

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


## PROCCESS

* create a process in background:
>ping google.com &
_The __&__ at the end sends the process at bg_ <br/>

* suspend a process (_ctrl+z_)
* cancel a process (_ctrl+c_)

* send to front or get back from suspended process:
>fg

* send to background or get back from suspended process:
>bg

* see process in the current terminal:
>jobs

* modify on certain job:
>fg %1
>bg %2
>fg %%
>bg %+
>fg %-
_Where % help us to tell the process number_ <br/>
_%% and %+ represent current job_ <br/>
_%- represent the previous job_ <br/>

* list process in the current shell
>ps

* list ALL system process:
>ps -e

* list ALL system process in complete format:
>ps -ef

* finish a process:
>kill 7172
_where 7172 is the process number_ <br/>


## APT
_Advanced Package Tool_ <br/>

* update
>apt update

* upgrade
>apt upgrade

* search a package
>apt-cache search rails

* description of a package
>apt show rails

* install a package
>sudo apt install rails

* remove a package
>sudo apt remove rails

* remove ALL from a package and user configuration files
>sudo apt remove --purge rails

* delete dependencies from a package
>sudo apt autoremove

* list installed packages in the system
>dpkg -l

* show detailed information about a package
>dpkg -s packagename


## PROGRAMMED TASKS

### cron

* Daemon that allow you the execution of tasks
* We can find them in _/etc/cron.*_
* The '*' could be: __daily, hourly, monthly, weekly__
* We can add our tasks in the __/etc/crontab__ file
>cat /etc/crontab
* Select editor:
>crontab -e
* Choose editor again:
>select-editor


## MONITORING

* The common commands to see a file are: _head_ and __tails__
* _head_ list first lines
* _tails_ list last lines, and it is very __useful__ for logs
>tails -f log.txt
* The parameter _"-f"_ (__follow__) is useful to update constantly the output
* __watch__ is very useful to repeat a command every 2 secs. to see differences
* We can use -n _x_ where "x" is the number of seconds
* Used in the commands: __ls -al__, __top__, __w__, __free__
* Stop watch: _ctrl+c_

### Logging

* Are saved in __/var/log__
>tail -5 /var/log/auth.log

* Record for event session:
>who /var/log/wtmp

* Kernel records from devices attached to system:
>dmesg

* Records from __systemd__
>jornaulctl
* __-r__ revere order
* __-f__ follow, to update new lines
* __u__ specify a unit
>journal -r -f -u NetworkManager

 * __free__ information about memory. _-m_ or _-g_ megas or gigas
 * __df__ disk free. _-h_ human version



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


## WHOIS

* In some countries is not allowed to show data from __whois__
* In other countries, some domain __registrars__ charge for hide this information
* __viewdns.info__

### Certificate Transparency: The New WHOIS

* WHOIS data is no longer readily available
* There is another source through the Certificate Transparency service

---

Web browsers do a good job in detecting malicious websites. <br/>

By using __SSL/TLS certificates__ and employing __HTTP Strict Transport Security__ 
features on web servers, browsers can identify an imposter site 
attempting to impersonate a legitimate one. <br/>

However, what browsers don't do well is identify the presence of 
a malicious certificate issued by a Certification Authority _(CA)_ <br/>

__Certificate Transparency__ is a requirement for CAs where they must publish records of 
all issued certificates. <br/>

The records data undergoes scrutiny and audits, allowing other CAs to identify 
any suspicious activity. <br/>

---

* We can check the available Certificate Transparency search services from 
various sources, for example: __https://crt.sh__ <br/>

* We can check __WEBBACK MACHINE__ for older versions of webs.

## EMAIL FOOTPRINTING

* Is the process of gathering emails accounts
* We can search in google, but there are other tools
* Email accounts may have a format like name.surname
* We can use harvester in _Kali Linux_
* The command _theHarvester_ by itself, give us help
* Lets get 5 email accounts from udg.mx from bing:
>theHarvester -d udg.mx -b bing -l 5

* Also can use: 
>https://haveibeenpwned.com
>https://www.osintframework.com/
>https://spiderfoot.net.


## SCANNING
__Active Footprinting or OSINT__

* Discover Active Hosts to get a list of IP addresses
* Discover open ports in every IP address
* identify software 
* Discover OS

### Six Flags of TCP

* __SYN__ The beginning of 3-Hand-shake
* __ACK__ Confirm the reception of a transmission and secuence number
* __PSH__ When 1 the receiver must inform about stored data
* __URG__ When 1, receiver gives priority and stop other processes
* __FIN__ When 1, there will not be more transmisions
* __RST__ When error, turns to 1. Useful to scan ports

### 3 Hand Shake

>PC sends __SYN, 100__ to SERV
>SERV sends __ACK, 101__ and its __SYN, 200__ to PC
>PC responds with __ACK, 201__
* Now there is a __connection__

### Test the 3 Hand Shake

_PC1_ <br/>
* Init a service of __Netcat__ 
* Active Listening, Disable name resolution, Verbose and add port 50000
>nc -lnvp 50000

_PC2_ <br/>
* Open _wireshark_
* Use filer: xxx.xxx.xxx.xxx and not arp (x...->PC1 IP address)
* In terminal:
>nc -nvv xxx.xxx.xxx.xxx 50000
* We can send messages from terminal
* _Ctrl+c_ to cancel communication

### Test UDP

* The same, but command for PC1:
>nc -lunvvp 60000
* Command for PC2:
>nc -nvvu xxx.xxx.xxx.xxx 60000
* We can see that _wireshark_ does not show anything, until we send messages

### Active Hosts Detection

We must use plenty of tools to detect host

__Netdiscovery__ <br/>
* uses ARP _(Address Resolution Protocol)_
* Devices send ARP requests as broadcast type
>sudo netdiscover -r 192.168.132.0/24 -i eth0

__Nmap__ <br/>
* A variant for Nmap is _-sn_ and works with:
* ICMP Ping Requests
* TCP SYN Scan at 443 port
* TCP ACK Scan at 80 port
* A ICMP time-stamp request
>sudo nmap -sn 10.0.0.0/24

* In Kali do a ping sweep:
>fping -a -g 192.168.10.0/24 2> /dev/null

* Now an ARP request:
>sudo netdiscover -r 192.168.10.0/24

* Composed ping:
>sudo nmap -sn 192.168.10.254 -T4 --disable-arp

#### TCP Connect Scanning

* Use it when you can not do a TCP SYN scanning
* Use it if you do not have root permissions
* Do not use TCP connect _if you have TCP SYN_
* TCP Connect uses the Operative System to stablish connections
* The OS stablish a TCP connection with the target and its ports
* The OS stablish the 3 hand-shake
>nmap -sT 192.168.132.1

#### TCP SYN Scanning

* Known as _stealthy_ scan
* Start, but do not complet the whole process of 3 Hand-shake
* In the 3rd step, sends __RST__
>sudo nmap -sS 192.168.132.1

#### UDP port Scanning

* DNS, NTP, SNMP use UDP
* You must always include a UDP Scan in a penetration test
* Used to be _very slow_
>sudo nmap -sU 192.168.132.1
* If port is open, the application responds
* The Scan registers the _datagram_
* The Scan responds with a __ICMP packet__ _"port unreachable"_

#### Range of Ports Scanning

* We can give a range of ports as a parameter with __-p__
>sudo nmap -sS 192.168.132.1 -p 1-100
>sudo nmap -sS 192.168.132.1 -p 137-139, 145
* We can see open ports:
>netstat -antup | less
>netstat -antup | grep :511
>netstat -antup | grep udp 











# 👁️👁️  

## Nessus

* Register on: http://www.tenable.com/products/nessus-home/ <br/>
* Open a __root__ terminal and go to Download folder <br/>
* __dpkg -i__ and add the file name <br/>

>You can start Nessus Scanner by typing /bin/systemctl start nessusd.service
>Then go to https://kali:8834/ to configure your scanner


