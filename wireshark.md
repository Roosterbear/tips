#      👁️👁️  

# WHIRESHARK

Its a tool for: <br/>

* Capturing
* Presenting
* Analyzing traffic from a network interface


Works on: <br/>

## TCP/IP

Sends data in little packages <br/>

It has 4 layers:

* Network Access (Ethernet)
* Internet (IPv4)
* Transport (UDP, TCP)
* Application (DNS, TLS)

### Router

Divides Broadcast Domains <br/>


### Switch

Divides Collision Domains <br/>


Includes: <br/>

_npcap_ driver for link layer for Windows <br/>

_Libpcap_ driver for link layer for Linux <br/>

_Dumpcap_ Capture Engine <br/>


## SECTIONS

We have 3 basic panels:


### Package list panel

Every little package in a row. <br/>


### Details panel

It has two sections: <br/>

* Metadata from Wireshark
* TCP/IP Headers


### Bytes panel

Info in hexadecimal and ASCII <br/>



## SOCKET

Is the __IP Address__ and the __Port__ <br/>

Note that in Wireshark, by default, we have not a port column. <br/>
We can add a column with Source and Destination ports easily: <br/>

* Select a __packet__
* Go to __Detail Panel__
* Open __Transmission Control Protocol__
* Right click on __source port__
* Select __Apply as Column__






