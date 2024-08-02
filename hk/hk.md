# I am the 👁️  in the sky 🔓










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

---
---

## TIP for MAC 🍎 
To access a folder in our network, we choose "Go" in the main menu. <br/>
Then "Conect to server" <br/>
Write, for example: "smb:\\172.16.xxx.xxx"<br/>

