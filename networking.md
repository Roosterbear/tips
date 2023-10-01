## NETWORKING

__NAT:__ _Network Address Translation_ <br/>

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


