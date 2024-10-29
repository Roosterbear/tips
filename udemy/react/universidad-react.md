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

### COMPONENTES

* Tan solo SON UNA FUNCION que retorna un valor
* PODEMOS USAR LA FUNCIÓN FLECHA
* Si solo agregamos el COMPONENTE podemos omitir el return 
* Si el retorno es simple, usamos UNA sola linea
* Si regresamos varias lineas, usamos PARÉNTESIS.

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

> Si __BORRAMOS__ el contenido de source y dejamos un archivo index.js
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
> OJO:
> Ya no se utiliza __ReactDOM.render__
> Ahora se importa: __import ReactDOM from 'react-dom/client'__



### INSERTANDO EXPRESIONES

```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const name = 'Luis Fernando'
const App = <h1>Hola { name }</h1>

ReactDOM.render(App, document.getElementById('root'))
```

### CREANDO UN COMPONENTE

> Observa como mandamos "App" al DOM
> Aun estamos trabajando al estilo __REACT 17__

```javascript
import React from 'react'
import ReactDOM from 'react-dom'

const name = 'Luis Fernando'
const App = ()=>(
  return <h1>{name}</h1>
)

ReactDOM.render(<App />, document.getElementById('root'))
```


### PROPS

> Son tubos por los cuales alimentamos a nuestro componente
> LAS ENVIAMOS COMO PRIMER PARÁMETRO DE NUESTRO COMPONENTE
> OJO:
> Asi es como ya trabaja __REACT 18__


```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'


const Fruta = (props)=>{
  return (
    <>
      <h1>{props.name}</h1>
      <hr/>
    </>
  )
}

const App = ()=>{
  return (
  <div>
    <Fruta name={"Higo"} />
    <Fruta name={"Mamey"} />
    <Fruta name={"Kiwi"} />
  </div>)
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <App/>
)

```
> No se exige poner los strings entre llaves
> Para otro tipo de datos se exige envolverlos con llaves
> Es por ello que se recomienda siempre usar __llaves__


### Aplicar Estilo

> No debemos usar guiones, sino camelCase
> Cualquier propiedad va entre comillas


```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'


const Fruta = (props)=>{
  const estilo = {    
    marginBottom: '1em',
    padding: '12px',
    borderRadius: '0.3em',
    backgroundColor: '#ffb000'
    
  }

  return (    
    <>
      <h1 style={estilo}>{props.name}</h1>
      <hr/>
    </>
  )
}

const App = ()=>{
  return (
  <div>
    <Fruta name={"Higo"} />
    <Fruta name={"Mamey"} />
    <Fruta name={"Kiwi"} />
  </div>)
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <App/>
)

```
> Si pasamos un valor Booleano __true__, solo se pasa el nombre:

```jsx
<Fruta podrida />
```
> Que equivale a:

```jsx
<Fruta podrida={true} />
```


### Módulos CSS

1. Agregar 'module' al nombre del archivo:
> TarjetaFruta.module.css

2. Importar con un nombre deseado:
> import estilos from './TarjetaFruta.module.css'

3. Aplicar clases:
> estilo.tarjeta
> estilo['tarjeta-activa']



### Modularización de componentes

1. Crear una carpeta por componente
> Ejemplo: TarjetaFruta.js

2. Dejar ahi el .css y el .js
> components/TarjetaFruta/TarjetaFruta.js
> components/TarjetaFruta/TarjetaFruta.css

3. Agregar un index.js que llame al componente:
> export {default} from './TarjetaFruta'

4. Al tener un index, solo importamos:
> import TarjetaFruta from './components/TarjetaFruta'



### Portales

> ?









