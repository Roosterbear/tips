# I am the 👁️  in the sky 🔓

 <br/>

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

>For bundle file, change permissions, and run it with __sudo ./VMWare__...

__Kali Linux__ <br/>

Now download Kali Linux for your VM software. <br/>

>Uncompress and move the folder to /home/Virtual Machines, you can rename it as just Kali.

Choose Open Project and then select the folder Kali <br/>

>user: kali, password: kali

Now download a Vulnerable Machine:

>Go to vulnhub.com and search for tr0ll1

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

>sudo apt-get update

>sudo apt-get install snort


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
_maybe, we can get a filtered state, but could be closed_ <br/>
_send a scan without flags with -sN to see if they are opened_ <br/>

>sudo nmap -sN -p 22,80 $IP

---

---

#      👁️👁️  

## WHIRESHARK

_npcap_ driver for link layer for Windows <br/>

_Libpcap_ driver for link layer for Linux <br/>

---

_Dumpcap_ Capture Engine <br/>


__SECTIONS__ <br/>

We have 3 basic panels:

_package list_ <br/>
Every little package in a row. <br/>

_package details_ <br/>
It has two sections: <br/>
<br/>

* Metadata from Wireshark
* TCP/IP Headers


_package list_ <br/>

<br/>

__TCP/IP__ <br/>

Sends data in little packages <br/>

It has 4 layers:

* Network Access (Ethernet)
* Internet (IPv4)
* Transport (UDP, IP)
* Application (DNS)




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

