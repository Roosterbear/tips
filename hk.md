# I am the 👁️  in the sky 🔓

## ---VIRTUALIZATION---

You can get Virtualbox or __VMWare Workstation Player__ for free. <br/>

* For bundle file, change permissions, and run it with __sudo ./VMWare__...

* Uncompress the Kali Linux and move the folder to /home/Virtual Machines, you can rename it as just Kali.

* Choose Open Project and then select the folder Kali

>user: kali, password: kali

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


### Preparing Target Metasploitables

* Like the Attaker VM, install Metasploitable1 (Windows Server 2008) Target (vagrant/vagrant)
* Open as Administrator a CMD window and type:
>slmgr /rearm
* Reboot the VM from the command line with:
>shutdown -r -t 0
* Now the desktop will be clean and no messages from activations will appear
* with VMWare Pro, shutdown the Metaspolitable and save a snapshot
* In the Windows 10 VM, use the same configuration as the last one (Users/Passw0rd!)
* Install the Metasploitable2 (msfadmin/msfadmin)













# 👁️👁️  

## Nessus

* Register on: http://www.tenable.com/products/nessus-home/ <br/>
* Open a __root__ terminal and go to Download folder <br/>
* __dpkg -i__ and add the file name <br/>

>You can start Nessus Scanner by typing /bin/systemctl start nessusd.service
>Then go to https://kali:8834/ to configure your scanner


