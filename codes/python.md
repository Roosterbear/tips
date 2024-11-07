# APUNTES DE PYTHON DE CÓDIGOS

## IMPORTACIONES

### Importar TODO el módulo

> Para usarlo, debemos hacer referencia a él

```python
import math
result = math.sqrt(16)
```


### Importar ciertas funciones

> Las usamos directamente

```python
from math import sqrt, pi
```


### Importar TODO con un Alias

> Usado para nombres de módulos muy largos

```python
import math as m
```


### Importaciones NO recomendadas

> Con alias en las funciones
> PODRIA SER CONFUSO

```python
from math import sqrt as s, pi as p
```

> Importar TODO en el espacio de nombres actual
> PODRÍAMOS TENER CONFLICTOS DE NOMBRES

```python
from math import *
```

## Requests

> Nos sirve para hacer solicitudes HTTP

### requests.get(url)

```python
import requests
response = requests.get('https://jsonplaceholder.typicode.com/comments')
print(response.text)
```


### deque

> Es una cola de __doble extremo__
> Para usar __deque__ necesitamos importarla

```python
from collections import deque

user_url = str(input('[+] Enter target URL to scan: '))

# Creamos una cola con deque
# Y agregamos lo que nos mande el usuario
urls = deque([usr_url])

# Para sacar el primer elemento de la izquierda:
# Para sacar elementos a la derecha, solo se usa pop
cola = urls.popleft()
print(cola)

```



## BeautifulSoup

> bs4 es la libreria de BeautifulSoup
> sirve para extraer datos de archivos HTML
> usada para el web scrapping






















































