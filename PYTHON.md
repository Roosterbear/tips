# PYTHON

## VIRTUAL ENVIRONMENT

### Create the Virtual Environment

>python3 -m venv <carpeta>

### Activate the Virtual Environment

* Vamos a la carpeta que creamos y luego a __bin__

>source activate

### Exit Virtual Environment

>deactivate


## PRINT

* In v3 you need parenthesis 

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

### CLASSES

```python
class Car:
  def __init__(self,color):
    self.color = color

  def show_color(self):
    print("This car is {}".format(self.color))

  car = Car("Black")
  car.show_color()
```

### FILES

* READ

```python
mafile = open("file.txt","rt")
data = mafile.read()
print(data)
```
>Where "rt" is "read - text", that means, "read only for a text file"

* WRITE

```python
mafile = open("file.txt","wt")
mafile.write("This text will erase the last one")
```

* APPEND

```python
mafile = open("file.txt","at")
mafile.write("This text will be below the last one")
```

* DELETE

```python
import os
os.remove("file.txt")                       
```

* SAVE BINARY FILE

```python
import pickle

malist = ["blue", "red", "black", "green"]

mafile = open("file.pckl","wb")
pickle.dump(malist,mafile)
mafile.close()
```

* READ BINARY FILE

```python
import pickle

mafile = open("file.pckl","rb")
llf = pickle.load(mafile)

print(llf)
```



### LAMBDA

We can use __lambda__:

>variable = lambda parameter:use of parameter

```python
answer = lambda number: number*2
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

