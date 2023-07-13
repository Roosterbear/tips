# I am the 👁️  in the sky 🔓

 <br/>

## DICTIONARY

__ARP__ (Address Resolution Protocol) - Gets MAC Address of a device.
__ICMP__ (Internet Control Message Protocol)
__IDS__ (Intrusion Detection System)


__active virtualization on windows__ <br/>
task manager - more details - performance - virtualization (is it disabled?) <br/>
reboot <br/>
enter BIOS <br/>

Acer    | Esc, F12, F9 <br/>
Asus    | Esc, F8 <br/>
Dell    | F12 <br/>
HP      | F9 <br/>
Lenovo  | F12, F8, F10 <br/>
Samsung | Esc, F12, F2 <br/>
Toshiba | F12 <br/>

Look for virtualization names like: VT-x, AMD-V, SVM, Intel Virtual Technology or Vanderpool <br/>

__virtualization__ <br/>

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

__Kali Linux__ <br/>

Now download Kali Linux for your VM software. <br/>


__information about a site ⛏️__ <br/>
_ping_ google.com <br/>
_nslookup_ google.com <br/>
__ipinfo.info__ <br/>
_whois_ google.com <br/>


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

## NMAP

_get a variable for a IP address_ <br/>
_scan to avoid firewalls that blocks ICMP_ <br/>

```terminal
export IP="192.168.1.126"
sudo nmap -PR $IP
```
_maybe, we can get a filtered state, but could be closed_ <br/>
_send a scan without flags with -sN to see if they are opened_ <br/>

```terminal
sudo nmap -sN -p 22,80 $IP
```

