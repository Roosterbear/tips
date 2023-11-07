# PYTHON

Python by all means <br/>

## PRINT

```python
print("Hello World !")
```

## INPUT

```python
print("Hola " + input("Como te llamas: "))
```

## VARIABLES

```python
name = input("Como te llamas? ")
print("Mucho gusto "+name+", mi nombre es Mishelin")
```

## LEN

```python
name = input("Como te llamas? ")
print("Mucho gusto "+name+", mi nombre es Michel")
print("...sabias que tu nombre tiene "+str(len(name))+" letras?")
```

## RANDOM

```python
import random

random_int = random.randint(1,6)
print(random_int)
```

## FOR

```python
lista = {1,2,3}
for i in lista:
  print(i)
```
__for in__ <br/>

```python
for i in range(3):
  print("Hola")
  print(i)
```
Numbers from 0 to 2 <br/>


```python
for i in range(1,10):
  print(i)
```
Numbers from 1 to 9 <br/>


```python
for i in range(2,10,2):
  print(i)
```
Numbers from 2 to 8 <br/>


```python
print([ _ for _ in range(10) if _ % 2 == 0])
print([ i for i in range(10) if i % 2 == 0])
```


## IF

```python
pase = 1
if pase == 1:
  print("Tienes acceso, ADELANTE!")
```


### GUESSING A LETTER

```python
word_list = ["abeja","boa","camello"]
import random
chosen_word = random.choice(word_list)
guess = input("Guess a letter: ").lower()
for c in chosen_word:
    if c == guess:
        print("Right")
    else:
        print("wrong")
```







# 👁️👁️  

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

