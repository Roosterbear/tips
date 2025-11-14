<h1 style="color:#00b4d8">Cybersecurity</h1>

# Foundations of Cybersecurity 🔐🔐🔐🔐🔐🔐🔐

> Detect and respond to attacks 
> Monitoring and protecting networks 
> Investigating incidents 
> Write code to automate task 

* __PII__ - Personal Identifiable Information
* __SPII__ - Sensitive Personal Identifiable Information

## CIA Triad 

__Is a guide or model that inform about organization risk__ <br/>

- __Confidentiality__ - Only authorized user can access _SPECIFIC_ assets or data
- __Integrity__ - Data is _CORRECT_, authentic and reliable
- __Availability__ - Data is accesible to those who are _AUTHORIZED_ to access it

# Play Safe: Manage Security Risks 🔐🔐🔐🔐🔐🔐🔐

__THREAD__

> Any circumstance or event that can _negatively impact_ assets 

__RISK__ 

> The posibility of a threat to impact the confidentiality, 
> integrity or availability of an asset.

__VULNERABILITY__ 

> A weakness that can be exploited by a threat. 
> [Outdated firewall-software, weak password, unprotected data and PEOPLE] 


## INCIDENT RESPONSE

1. Mitigate potential impact
2. Documenting procedures
3. Establishing staffing plans
4. Educating users
5. Sets the Foundation for successful incident response

<br/>

# Connect and Protect: Networks and Network Security 🔐🔐🔐🔐🔐🔐🔐

__Simple Network Management Protocol [SNMP]__
> Used to monitor and manage devices. 
> Can restore a password or change basic configuration.
> Also can ask requests to get information about used bandwith.
> Is on _Application_ Layer.

__Internet Control Messages Protocol [ICMP]__
> Used to get information about transmission errors between devices. <br/>
> Also is a fast solution to connectivity issues like latency
> by using the _ping_ command. <br/>
> Is on _Internet_ Layer. <br/>
> An internet protocol used by devices to tell each other about
> data transmission error across the network. <br/>

__Post Office Protocol [POP]__
> _Application_ Layer to manage emails <br/>
> Ports _110_ (not encrypted) and _995_. <br/>

__Internet Messages Access Protocol [IMAP]__
> Downloads the headers and uses _143_ (not encrypted) and _993_ for TSL.

__Simple Mail Transfer Protocol [SMTP]__
> Routes and transmites emails and works with 
> the software Message Transfer Agent [MTA]
> Uses the _25_ (not encrypted) and _587_ for TSL.

__Hyper-Text Transmission Protocol - Secure [HTTPS]__
> Secure method of communication between server and client.
> Uses Secure Sockets Layer __[SSL]__ and Transport Layer Security __[TSL]__
> Uses port _443_ and is on _Application_ Layer.

__Secure File Transfer Protocol [SFTP]__
> Uses the __[SSH]__ Secure SHELL Protocol and 
> __[AES]__ Advanced Encryption Standard.
> Is on _Application_ Layer. Port _22_ 


* IEE 802.11 Starndards for Wireless

1. __[WEP]__ Wired Equivalent Privacy - _1999_
2. __[WPA]__ WiFi Protected Access - _2003_
  - Uses Temporal Key Integrity Protocol __[TKIP]__
3. __[WPA3]__ Uses Simultaneous Authentication of Equals __[SAE]__


## FIREWALLS

> There are _HARDWARE_ and _SOFTWARE_ firewalls.

__STATEFUL__ [+]
> A class of Firewall that keeps track of information
> passing through it and proactively filters out threats.

__STATELESS__ [-]
> A class of Firewall that operates _BASED ON PREDEFINED RULES_
> and does not keep track of information from data packets.

__Denial of Service Attack [DoS]__
> An attack that targets a network or server and _floods it_ 
> with network traffic to disrupt the normal business operation 
> by overloading the organization's network.

__Distribuited denial of service attack [DDoS]__
> A type of denial of service attack that uses _multiple devices_ or servers 
> in _different locations_ to flood the target network with unwanted traffic.

__SYN flood attack__
> A type of DoS attack that simulates a TCP connection
> and floods a server with SYN packets.

__ICMP flood__
> A type of DoS attack performed by an attacker
> repeatedly sending ICMP packets to a network server.

__Ping of Death__
> A type of DoS attack caused when hacker pings a system by sending it
> an oversized ICMP packet that is bigger than 64Kb.

__tcpdump__
> Command Line Network Protocol Analyzer.
> Brings a brief packet analysis, converts key information about network traffic.
> Shows the source and destiny IP address and also the ports used in communications.

__Passive packet sniffing__
> A type of attack where data packets are read in transit.

__Active packet sniffing__
> A type of attack where data packets are manipulated in transit.

__IP Spoofing__
> A network attack performed when an attacker changes the source IP
> of a data packet to impersonate an authorized system and gain
> access to a network.

__On-path attack__
> An attack where a malicious actor places themselves in the middle of an
> authorized connection (IP spoofing) and intercepts or alters the data transit.

__Replay attack__
> A network attack performed when a malicious actor intercepts a data packet
> in transit and delays it or repeats it at another time. Use IP spoofing.

__Smurf attack__
> A network attack performed when an attacker sniffs
> an authorized user's IP and floods it with packets.

__Multi-factor authentication [MFA]__
> A security measure which requires a user to verify their identity
> in two or more ways to access a system or network. 

* Something you know
* Something you have
* Something unique about you

__Brute force attack__
> A Trial and Error process to discover private information and could be:

* Simple - Trying any combination.
* Dictionary - Using a list.

__Virtual Machines [VM]__
> Physical computers in software versions. Give us an additional layer of security.
> Can be very helpful to test.

__Sandboxes__
> A test area to exec software out of our network, 
> try patches, suspicious software (or files), 
> identify errors, detect vulnerabilities 
> and simulate scenarios of an attack. 

__Hashing__ 
> Uniderectional function that converts information 
> in an unique value to determine its integrity.

__Salting__
> Adds random characters to Hash passwords, 
> increasing length and complexity of values, 
> making them more secure.

__Multifactor Authentication [MFA]__
> Security measure that ask a user for 2 or more ways of authentication.
> __[2FA]__ Two Factor Authentications have only 2 ways of verification.

__Completely Automated Public Turing Computers and Humans Apart [CAPTCHA]__
> Is a challenge-response authentication by a simple test, 
> preventing a password to be forced.
> reCAPTCHA is a Google Service.

__Password Policies__
> Good practices in patterns of complexity, 
> frequency in updates and login attempts 
> before the account is suspended.

__PORT Filtering__
> Allow access to most used ports for normal operations of a network.
> Block any port that is not used.

__Intrusion Detection System [IDS]__
> Monitor the activity of a system and _alerts_ about intrusions.
> Based on malicious traffic signatures and known attacks.
> Do not stop the traffic and is before a FIREWALL.

__Intrusion Prevent System [IPS]__
> Monitor the activity of a system and take action or _stops_ traffic.
> Can be false positives, and break the legitemate traffic.

__Security Information and Event Management__ [SIEM]
> A tool that gathers and analyzes logs from IDS, IPS, Firewalls, VPN, proxies
> and DNS in real time.

# Tools of the Trade: Linux and SQL 🔐🔐🔐🔐🔐🔐🔐
## LINUX
__Unified Extensible Firmware Interface [UEFI]__
> A microchip that holds load instructions in moderns computers, replacing BIOS.
> Provide enhanced security functions
<br/>
Commands: <br/>
* __cat__   Displays the content of a file
* __cd__    Navigates between directories
* __pwd__   Prints the working directory onto the screen
* __ls__    Displays the names of files and directories 
            in the current working directory 
* __head__  Show first 10 lines 
* __tail__  Show last 10 lines 
* __less__  A page at a time of a file 
            space - next page 
            b - previous page 
            Down arrow - advance a line 
            Up arrow - back a line 
            q - exit 
---

* [grep]    Searches a specified file and returns all lines <br/>
            in the file containing a specified string <br/>
* [Pipping] Sends the _standard output_ of one command as _standard input_ to another<br/>
            command for further processing, using the pipe (|)character. <br/>
* [find]    used to search directories and files that meet specified criteria <br/>
            -name -  distinguishes names in upper / lowercase <br/>
            -iname - no matter upper / lowercase <br/>
            -mtime - -3 (_Days ago_) <br/>

__Permissions__ <br/>

The type of access granted for a file or directory. <br/>
Are represented for 10 characters: <br/>

> drwxrwxrwx <br/>

[d]   Indicates if is a directory, instead [-] indicates that is a file. <br/>
[rwx] The first 3 group of rwx indicates the _user_ type permissions. <br/>
[rwx] The second 3 group of rwx indicates the _group_ type permissions. <br/>
[rwx] The third 3 group of rwx indicates the _other_ type permissions. <br/>

__Types of permission__<br/>
[read]    Contents on the file can be read. Represented by [r] <br/>
[write]   Allows modifications of contents of the file. Represented by [w] <br/>
[execute] Execute a file or access files in a directory. Represented by [x] <br/>

__Types of owners__ <br/>
[user]  The owner of a file. Represented by [u]<br/>
[group] Multi-user environment. Represented by [g] <br/>
[other] Anyone else. Represented by [o] <br/>

__Listing files__ <br/>
* ls -l - Displays permissions to files and directories. <br/>
* ls -a - Displays hidden files. <br/>

- Hidden files starts with "." <br/>

__chmod__ <br/>
It changes permission on files and directories. <br/>
[+] Add a permission. <br/>
[-] Take permission away. <br/>
[=] Assign permissions to user, groups or other. <br/>

```bash
chmod u+rwx,g-x login_sessions.txt
chmod u=r,g=w login_sessions.txt
```
__useradd__ <br/>
Adds a user to the system. <br/>

__userdel__ <br/>
Deletes a user from the system. <br/>

__usermod__ <br/>
Modify user account. <br/>
[-g] Set main group. <br/>
[-G] Set additional group. <br/>
[-l] Changes user name. <br/>
[-L] Blocks a user account. <br/>
[-d] Changes directory. <br/>

__groupdel__ <br/>
Deletes a group. <br/>
_Remember:_ <br/>

> When we creates a new user, a new group of the same name is created. 

__man__ <br/>
> Displays information on other commands and how they work. 

__whatis__ <br/>
> Displays a description of a command on a single line. 

__apropos__ <br/>
> Searches the manual page descriptions for a specified string. 
> [-a] -> Will return only the commands that contain both strings. 


## SQL
__Primary Key__ <br/>
A column where every row has a unique entry. Can only be one primary key. <br/>

__Foreign Key__ <br/>
A column in a table that is a primary key in another table. <br/>

__Query__ <br/>
A request for data from a database table or a combination of tables. <br/>

__SELECT__ <br/>
Indicates which columns to return. <br/>

__FROM__ <br/>
Indicates which table to query. <br/>

__ORDER BY__ <br/>
Order the records returned by a query in sequence, <br/>
and specify the column on which to base. <br/>

__Filtering__ <br/>
Selecting data that match a certain condition. <br/>

__WHERE__ <br/>
Indicates the condition for a filter. <br/>

__LIKE__ <br/>
Used with WHERE to search for a pattern in a column. <br/>

__NULL__ <br/>
> Represents a missing value due to any reason.

# Assets, Threats and Vulnerabilities 🔐🔐🔐🔐🔐🔐🔐

__Hash Function__ <br/>
An algorithm that produces a code that _CAN'T BE DECRYPTED_. <br/>

```bash
sha256sum newfile.txt
```
> [SHA] Secure Hash Algorithm (SHA-1, SHA-224, SHA-256, SHA-384, SHA-512)

__Non Repudiation__ <br/>
>The concept that the authenticity of information can't be denied. 

__Rainbow Tables__ <br/>
> Is a file with weak passwords and their hashes. 

__Salting__ <br/>
> Additional protection to strengthen hash functions. 
> Is a random chain of characters added BEFORE hashing. 

__Comparing__ <br/>

```bash
sha256sum file1 >> hashed1
sha256sum file2 >> hashed2
cmp hashed1 hashed2
```

__Factors of AUTHENTICATION__ <br/>
[Knowledge] Something that the user knows <br/>
[Ownership] Something that the user possesses <br/>
[Characteristic] Something the user is <br/>

[MFA] __Multi-Factor Authentication__ <br/>

> A security measure which requires a user to verify their identity 
> in two or more ways to access a system or network. 

__Mechanisms of AUTHORIZATION__ <br/>

__Separation of duties__ <br/>
The principle that users should not be given levels of authorization <br/>
that would allow them to misuse a system <br/>

__Basic auth__ <br/>
The technology used to establish a user's request to access a server <br/>


__OAuth__ <br/>
An open-standard authorization protocol that shares designated <br/>
access between applications. <br/>
Uses API tokens to verify access between you and a service provider. <br/>


__API Token__ <br/>
A small block of encrypted code that contains information about a user, <br/>
like permissions or user identity. <br/>

__Session__ <br/>
A sequence of network HTTP basic auth requests and responses associated <br/>
with the same user. <br/>

__Session ID__ <br/>
A unique token that identifies a user and their device while accessing the system <br/>

__Session cookie__ <br/>
A token that websites use to validate a session and determine <br/>
how long that session should last <br/>

__Session hijacking__ <br/>
An event when attackers obtain a legitimate user's session ID <br/>

__Cross-site scripting__ [XSS] <br/>
An injection attack that inserts code into a vulnerable website <br/>
or web application using [HTML] and [Javascript] <br/>
Can give access to session cookies, geolocation, webcams or microphones <br/>

There are 3 types: <br/>

1. __REFLECTED:__ <br/>
An instance when malicious script is sent to a server and activated <br/>
during the server's response <br/>

2. __STORED:__ <br/>
An instance when malicious script is injected directly on the server <br/>

3. __DOM-Based:__ <br/>
An instance when malicious script exists in the webpage a browser loads <br/>


# Sound the Alarm: Detection and Response 🔐🔐🔐🔐🔐🔐🔐

__Event__
> An observable occurence on a network, system or device

__The 5W's of an incident__
1. Who triggered the incident
2. What happened
3. When the incident took place
4. Where the incident took place
5. Why the incident occurred

__Intrusion Detection System (IDS)__
> An application that monitors system and network
> activity and produces alerts on possible intrusions

__Intrusion Prevention System (IPS)__
> An application that monitors system activity
> for intrusions and take action to stop the activity

__Detection Categories__ <br/>

1. Positive TRUE __Correct detection of a REAL incident__
2. Negative TRUE __No Malicious Activity and NO ALERTS__
3. Positive False __Alert triggers and there is NO REAL Incident__
4. Negative False __Malicious activity, but NO Alerts__

__(SIEM)__
> An application that collects and analyzes log data to monitor
> critical activities in an organization
> COLLECT, ANALYZE AND REPORT

__Comparison Operators__

|  | Type | Symbol | Abreviature |
| :---: | :---: | :-----: | 
| Equal | == | eq |
| Not Equal | != | ne |
| Greater than | > | gt |
| Less than | < | lt |
| Greater or Equal | >= | ge |
| Less or Equal | <= | le |

> You can use __and__, __or__, parentheses,  
> "_contains_" operator or regular expressions (_matches_). 

__Filters by protocols:__ <br/>

* dns
* http
* ftp
* ssh
* arp
* icmp

__Filtering IP address__

> ip.addr == 172.21.224.2

__Filtering IP source__

> ip.src == 172.21.224.2

__Filtering IP destination__

> ip.dst == 172.21.224.2

__Filtering MAC address__

> eth.addr == 00:70:f4:23:18:c4

__Filtering Ports__

> udp.port == 53
> tcp.port == 25


# Automate Cybersecurity Task with Python 🔐🔐🔐🔐🔐🔐🔐

__Conditionals__

```python
operating_system = 3
if operating_system < 3:
  print("Updates needed")
else:
  print("No updates needed")
  
```
__Loops__

```python
for i in range(3):
  print("No se pudo establecer la conexión")

```

__PEP (_Python Enhancement Proposals_) 8 style guide__
> A resource that provides stylistic guidelines
> for origrammers working in Python

__Indentation__
> Space added at the beginning of a line of code

__str()__
> Converts the input object into a string

__len()__
> Return the number of elements in an object
> Ex. id_chars = len(employee_id)

__method__
> A function that belongs to a specific data type

__.upper()__
> Returns a copy of the string in all uppercase letters

__.lower()__
> Return a copy of the string in all lowercase letters

__INDEX()__

> A number assigned to every element in a sequence of a STRING that indicates its position
> We can get more than 1 character with _slices:_
> Ex. print("Hello"[0:4]) returns "Hell". 
> The first number is the start, the second, where to stop (but not to show!)

__.index()__
> Method that finds the first occurrence of the input
> in a string and returns its location
> Ex. print("HELLO".index("E"))
> To find the index of letter "E" in "HELLO"

__.insert()__
> Adds an element in a specific position inside a list

```python
my_list = ["a","b","c"]
my_list.insert(1,"ab")
# now is ["a","ab","b","c"]
```
__.remove()__
> Removes the first occurrence of a specific element in a list

```python
my_list = ["a","b","c"]
my_list.remove("ab")
# now is ["a","b","c"] again
```
__Algorithm__
> A set of rules that solve a problem

## REGULAR EXPRESSIONS
### +
> Represents one or more occurrences of a specific character
> Ex. "a+" can get: "a", "aaaa"

### \w
> Matches with any alphanumeric character
> but it does not match symbols
> Ex. "\w" can get "1","c"

### \w+
> This combination can get: "security", "abc123", "192"

### .
> Any character

### \d

> All digits

```python
import re
print(re.findall("\d","h32rb17"))
# ['3','2','1',7']
```

### \s
> Spaces

### \.
> Period.

### Combinations

```python
import re
print(re.findall("\d+","h32rb17"))
# ['32','17']
```
```python
import re
print(re.findall("\d{2}", "h32rb17 k825t0m c2994eh"))
# ['32', '17', '82', '29', '94']
```
```python
import re
print(re.findall("\d{1,3}", "h32rb17 k825t0m c2994eh"))
# ['32', '17', '825', '0', '299', '4']
```
```python
# IP pattern !!!!
pattern = "\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}"
```
### with
> Handles errors and manages external resources

__open()__
> Opens a file in Python

```python
with open("login_atempts.txt", "r") as file:

```
__.read()__
> Converts files into strings

```python
with open("login_atempts.txt", "r") as file:
  file_text = file.read()

print(file_text)
```
## Parsing
> The process of converting data into a more readable format

__.split()__
> Converts a string into a list

```python
with open("login_attempts", "r") as file:
  file_text =  file.read()

usernames = file_text.split()

def login_check(login_list, current_user):
  counter = 0
  for i in login_list:
    if i == current_user:
      counter = counter + 1
  
  if counter >= 3:
    return "Cuenta bloqueada"
  else:
    return "You can log in"

login_check(usernames, "eraab")

```
# Put to Work: Prepare for Cybersecurity Jobs 🔐🔐🔐🔐🔐🔐🔐
> CISO: Chief Information Security Officer

## Escalation
> Tell a superior about a security incident

## Malware infection
> An incident type that occurs when malicious software designed to
> disrupt a system infiltrates an organization's computer or network

## Unauthorized access
> An incident type that occurs when an individual 
> gains digital or physical access to a system or
> application without permission
> __ALL UNAUTHORIZED ACCESS AND IMPROPER USAGE ARE IMPORTANT TO ESCALATE__

* __Bruce Force Attacks__
> Use trial and error to compromise passwords,
> login credentials and encryption keys.

## Improper Usage
> An incident type that occurs when an employee of an organization
> violates the organization's acceptable use policies

## Roles in Escalation
* Data owners
* Data controllers
* Data processors
* Data custodians
* Data Protection Officers

## Escalation Policy
> A set of actions that outline who should be notified
> when an incident alert occurs and how that incident
> should be handled

## Stakeholders
> An individual or group that has an interest in the decisions
> or activities of an organization

## Risk Manager Responsabilities
* Identify risks
* Manage the response to security incidents
* Notify the legal department
* Inform the organization's public relations team

## Job searching sites
* ZipRecruiter
* Indeed
* Monster Jobs

## STAR Method
> To answer "Tell about a time when you encountered a challenge on the job"

* __SITUATION__ - What was the SITUATION
* __TASK__ - What you had to DO
* __ACTION__ - What YOU DID to resolve the situation
* __RESULT__ - The problem RESOLVED

> What you don't know, BE HONEST
> You're a quick learner and eager to develop that SKILL