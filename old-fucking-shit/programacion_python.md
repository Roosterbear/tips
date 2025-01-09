# PYTHON

## LEN

```python
name = input("Como te llamas? ")
print("Mucho gusto "+name+", mi nombre es Michel")
print("...sabias que tu nombre tiene "+str(len(name))+" letras?")
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


### DICTIONARY

```python
dictionary = {
  "Bug":"An error in a program",
  "Function":"A piece of code"
}

# Agregar un elemento
dictionary["Loop"] = "The action of doing something over and over again"

# Obtener un elemento
print(dictionary["Bug"])

# Listas anidadas
travel = {
  "France":["Paris","Lille","Dijon"],
  "Germany":["Berlin","Hamburg","Stuttgart"]
}

```

### TUPLES

> Son como listas pero INMUTABLES

mi_tupla = (1,2,3,4,5,6,7)


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

# MODULE

> Usamos un modulo con import

```python
import turtle

tortuga = turtle.Turtle()
```

> Para utilizar con frecuencia algo del modulo
> conviene escribir lo siguiente

```python
from turtle import Turtle()

tortuga = Turtle()
```

> Podemos crear nuestro propio módulo

```python
# my_module.py
my_variable = "Hola desde Modulo"

# ejemplo.py
import my_module

print(my_module.my_variable)
```

## TURTLE

```python
from turtle import Turtle, Screen

tim = Turtle()
tim.shape("turtle")
tim.color("green")

for _ in range(4):
  # Go in pixels
  tim.forward(100)

  # Move in grades
  tim.left(90)

screen = Screen()
# Wait
screen.exitonclick()
```


## RANDOM

```python
import random

random_int = random.randint(1,6)
print(random_int)
```


## FILES

* READ

```python
with open("file.txt","r") as file:
  data = file.read()
print(data)
```
>Where "rt" is "read - text", that means, "read only for a text file"

* WRITE

```python
with open("file.txt","w") as file:
  file.write("Soy SATAN")
```

* APPEND

```python
with open("file.txt","a") as file:
  file.write("Soy SATAN")
  file.write("Rey SATAN, Rey Seguro")
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

### CSV

```python
import csv

with open("weather_data.csv") as data_file:
  data = csv.reader(data_file)
  temperatures = []
  for row in data:
    if row[1] != "temp":
      temperatures.append(int(row[1]))

  print(temperatures)
```

## LIST COMPREHENSION

> Cuando queremos crear una lista a partir de otra

```python
# Si tenemos una lista
numbers = [1,2,3]
# Y queremos crear una lista nueva con el doble de esos numeros
dobles = []
# Usamos este codigo
for n in numbers:
  doble = n + n
  dobles.append(doble)  
```

> Podemos crear esa lista con una sola linea

```python
numbers = [1,2,3]
dobles = [n + n for n in numbers]
```

## ARGUMENTOS

### Argumentos Avanzados

> Podemos poner valores por default

```python
def foo(a=1, b=2, c=3):
  print(a,b,c)

foo(4)
# Prints 4,2,3
foo(b=7)
# Prints 1,7,3
```

### Args

> Agregamos un parametro (args) antecediendo un asterisco
> Esto permite capturar varios argumentos en la funcion

```python
def sum(*args):
  resultado = 0
  for a in args:
    resultado += a

  print(resultado)

sum(2,6,9,8,1,2,3,4,6,7)
```

### Kwargs

> Básicamente es un diccionario que representa llaves y valores

```python
def calculate(**kwargs):
  print(kwargs)

calculate(add=3, multiply=5)
```


## Tkinter

### Ventana Sencilla

> Importamos:

```python
from tkinter import *

window = Tk()
window.title("Mi primera GUI")
window.geometry("800x600")
window.minsize(width=500, height=300) # Checa place y grid

# Label
my_label = Label(Text="Esto no se va a ver", font=("Arial",24, "bold"))
my_label.pack()

my_label["text"] = "New Text"
my_label.config(text="New Text")

# Button
def button_clicked():
  new_text = input.get()
  my_label.config(text=new_text)

button = Button(text="Click Me", command=button_clicked)
button.pack()

# Entry
input = Entry(width=10)
input.pack()

```

### Pomodoro Project

```python
from tkinter import *

# --- CONSTANTS ---
PINK = "#e2979c"
RED = "#e7305b"
GREEN = "9bdeac"
YELLOW = "#f7f5dd"
FONT_NAME = "Courier"
WORK_MIN = 25
SHORT_BREAK_MIN = 5
LONG_BREAK_MIN = 20

# --- TIME RESET ---

# --- TIME MECHANISM ---

# --- COUNTDOWN MECHANISM ---

# --- UI SETUP ---
window = Tk()
window.title("Pomodoro")



window.mainloop()
```






















## PANDAS

> Hay 2 tipos de datos en Pandas:

1. __Series__ - 1-dimensional
2. __DataFrame__ - 2-dimensional










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

