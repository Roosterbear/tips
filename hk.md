# I am the 👁️  in the sky 🔓

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

* For bundle file, change permissions, and run it with __sudo ./VMWare__...

* Uncompress the Kali Linux and move the folder to /home/Virtual Machines, you can rename it as just Kali.

* Choose Open Project and then select the folder Kali

>user: kali, password: kali

__Configuring the Network__<br/>

### Bridged Network

Connects the VM directly to the local network, it is another node with its own IP address. <br/>

### NAT (Network Address Translation)

Sets up a _private_ network on the host machine, all the traffic from the VM will appear to come from the host machine's IP address. <br/>

### Host only network

The VM will be able to communicate with other Virtual Machines in the host only network as well as the host, but it will not be able to connect with internet or the local network. <br/>


# 👁️👁️  

## Nessus

* Register on: http://www.tenable.com/products/nessus-home/ <br/>
* Open a __root__ terminal and go to Download folder <br/>
* __dpkg -i__ and add the file name <br/>

>You can start Nessus Scanner by typing /bin/systemctl start nessusd.service
>Then go to https://kali:8834/ to configure your scanner


