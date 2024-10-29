# UNIVERSIDAD REACT 20 Hrs.

## INTRODUCCION

### NPM

> Es un Repositorio y Gestor de Paquetes

### BABEL

> Transcribe Javascript Moderno a Código Compatible


### Webpack

> Crea módulos empaquetados para distribuir código
> Puede integrar código CSS, imágenes o Fuentes


### Chrome Dev Tools

> Se abren con la tecla __F12__ o con _ctrl+shift+i_




### CREATE-REACT-APP

1. Verificar que tengamos __NODE__:

> node -v

2. Verificamos que tengamos __NPM__:

> npm -v

3. Instalar create-react-app de forma global:

> npm install -g create-react-app

4. Verificamos que esté instalado:

> create-react-app

5. Crear nuestro primer proyecto:

> create-react-app mi-primer-proyecto



### ESTRUCTURA

* node_modules
> Todas las dependencias que se descargan para nuestro proyecto 

* public
> Encontramos el __index.html__
> En él se encuentra el id "__root__" donde se cargará el proyecto

* src
> Es donde vamos a trabajar

* package.json
> Es el archivo donde configuramos nuestro proyecto




## CORE

### CONCEPTOS BASICOS

> Existen 2 tipos de componentes:

* Funcionales
* De Clase

> Los componentes solo pueden:

* Empezar con una letra mayúscula
* Retornar un solo nodo


> Cuando usamos JSX como:

```jsx
var Title = <h1>Hola mundo</h1>
```

> Babel lo traduce a:

```javascript
var Title = React.createElement("h1",null,"Hola mundo");
```

> Si borramos el contenido de source y dejamos un archivo index.js
> Podemos poner cualquier código y funcionará:

```javascript
alert("Hola Mundo");
```


### INYECTANDO CONTENIDO EN EL DOM

> Si queremos utilizar React, importamos la librería React
> Si queremos usar el dom, importamos ReactDOM
> Todo se monta en el ID "root", así que obtenemos ese elemento
 
```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const App = <h1>Hola React</h1>
const root = document.getElementById('root')
ReactDOM.render(App, root)
```


### INSERTANDO EXPRESIONES

> Podemos 

```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const name = 'Luis Fernando'
const App = <h1>Hola { name }</h1>

ReactDOM.render(App, document.getElementById('root'))
```


### CREAR UN COMPONENTE













