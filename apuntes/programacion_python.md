# PYTHON

## PRINT

```python
print("Hello World !")
```

## INPUT

```python
print("Hola " + input("Como te llamas: "))
```
> Te pide tu nombre y luego imprime el texto con tu nombre


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

# MODULE

> Podemos crear nuestro propio módulo

```python
# my_module.py
my_variable = "Hola desde Modulo"

# ejemplo.py
import my_module

print(my_module.my_variable)
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

```python
#Numbers from 0 to 2
for i in range(3):
  print("Hola")
  print(i)
```

```python
#Numbers from 1 to 9
for i in range(1,10):
  print(i)
```

```python
#Numbers from 2 to 8 steps by 2
for i in range(2,10,2):
  print(i)
```

## IF

```python
pase = 1
if pase == 1:
  print("Tienes acceso, ADELANTE!")
```

### DICTIONARY

```python
dictionary = {
  "Bug":"An error in a program",
  "Function":"A piece of code"
}

#Add new item
dictionary["Loop"] = "The action of doing something over and over again"

#Retrieve an item
print(dictionary["Bug"])

#List nested in a Dictionary
travel = {
  "France":["Paris","Lille","Dijon"],
  "Germany":["Berlin","Hamburg","Stuttgart"]
}

```

### LISTS

```python
fruits = ["Apple", "Fig", "Blackberry"]

# Cambiar en cierto indice:
fruits[0] = "Mammee"

# Agregar al final
fruits.append("Kiwi")



```


```python
# Podemos imprimir directamente una lista
# Esa lista puede tener ciertas condiciones
print([ i for i in range(10) if i % 2 == 0])
# Podemos usar _ como variable
print([ _ for _ in range(10) if _ % 2 == 0])
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

