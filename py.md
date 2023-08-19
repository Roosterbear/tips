# PYTHON

## Python by all means

__sockets__ <br/>

A method to communicate between client and server <br/>

__subprocess module__ <br/>

```python
#!/usr/bin/env python
import subprocess
subprocess.call("ifconfig", shell=True)
```
__changing mac address__ <br/>

08:00:27:c5:0d:1c <br/>

```python
#!/usr/bin/env python
import subprocess
interface = raw_input("interface> ")
new_mac = raw_input("new MAC> ")
print("[+] Changing MAC Address for " + interface +" to " + new_mac)


subprocess.call("ifconfig " + interface + " down", shell=True)
subprocess.call("ifconfig " + interface + " hw ether", shell=True)
subprocess.call("ifconfig " + interface + " down", shell=True)
```
<!-- import argparse -->

