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

## BeautifulSoup

> bs4 es la libreria de BeautifulSoup
> sirve para extraer datos de archivos HTML
> usada para el web scrapping



## Requests

> Nos sirve para hacer solicitudes HTTP

### requests.get(url)

```python
response = requests.get('https://api.example.com/data')
print(response.text)
```

### requests.post(url, data)
### requests.put(url, data)
### requests.delete(url)
### requests.head(url)
### requests.options(url)
### requests.patch(url, data)
### requests.Session()




















































