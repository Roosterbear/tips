# WINDOWS TRICKS

## BAT (Command Line)

__@echo off__<br/>
- Removes the execution line of the command.
- If you want your script to look professional, is mandatory.

__pause__
- Use pause to stop the execution of a script and waits the user response.

__pause>nul__
- We hide the message "Presiona una tecla para continuar..."

__start__
- Opens files, web sites, etc.

__color__ [background][text]<br/>
The most used is 0F or 0A<br/>

| Code | Color |
| :---: | :---: |
| 0 | black | 
| 1 | blue |
| 2 | aquamarine |
| 3 | red |
| 4 | purple |
| 5 | yellow |
| 6 | black |
| 7 | white-gray |
| 8 | grey |
| 9 | light blue |
| A | light green |
| B | light aquamarina |
| C | light red |
| D | light purple |
| E | light yellow |
| F | white white |


### Tip #1 _run cmd always as admin_

* Run - cmd
* Right click - open file location
* Right click - properties - Run as administrator


### Tip #2 _curl_ 

_QR Code_ <br/>
>curl qrenco.de/https://google.com 

_A dictionary_ <br/>
>curl dict.org/d:word


### Tip #3 _delete temporary files_

>del /s /q c:\Windows\temp\*


### Tip #4 _hide a folder_

_invisible_ <br/>
>attrib +h +s +r foldername

_visible_ <br/>
>attrib -h -s -r foldername


### Tip #5 _saved networks_

>netsh wlan show profile
>netsh wlan show profile "wifinetwork" key=clear 
>netsh wlan show profile "wifinetwork" key=clear | findstr"Key Content"

```cmd
for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do
@if "%j" NEQ "" (echo SSID: %j & netsh wlan show profiles %j key=clear | 
findstr "Key Content")
```

>scp wifi.bat root@xxx.xxx.xxx.xxx:~/wifi.bat

### Tip #6 _history_

>doskey /history


### Tip #7 _change color_

>color 07
>color /?

### Tip #8 _change prompt and title_

>prompt hacker$G
>prompt beautiful hacker$G
>title Hackers

_return original_ <br/>

>prompt


## MMC (Microsoft Management Console)

This is a Standar Window 

__reliability monitor__ <br/>

Control Panel  - System and Security - Security and Maintenance - Maintenance - See reliability history <br/>

__event viewer__ <br/>

Control Panel  - System and Security - Administrative Tools - Event Viewer <br/>



## BIOS (Basic Input Output System) AND UEFI (Unified Extensible Firmware Interface)

They exist in ROM. BIOS has not inbuilt security and make it vulnerable to attaks.



## HYPER-V

To activate Hyper-V go to Control Panel - Programs - Uninstall Programs - Active Windows Characteristics

---

---

#      👁️👁️  

## ---SysInternals---

We need to download the suite from:

>https://learn.microsoft.com/en-us/sysinternals/downloads/

__Who is in our computer?__ <br/>

>logonsessions64.exe

__Explore proccesses__ <br/>

>procexp.exe

---

---

#      👁️👁️  

## ---Active Directory---

>Group Administration directives

* Domains controllers
* Elegir Grupo
* Configuracion de Equipo
* Configuración de Windows
* Configuración de Seguridad
* Directivas Locales

>Windows Defender

Choose Group (_Default Domain Policy_) - Edit (_right click_) <br/>
Computers - Directives - Administrative Templates - Windows Components - Endpoint Protection <br/>


>Active Directory Administration Center

We can search users by any criteria and apply <br/>
Then we can go to General Information and check the Windows Powershell History below <br/>


