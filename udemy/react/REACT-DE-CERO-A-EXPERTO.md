# REACT DE CERO A EXPERTO 54 Hrs.

- [REACT DE CERO A EXPERTO 54 Hrs.](#react-de-cero-a-experto-54-hrs)
  - [INTRODUCCION](#introduccion)
    - [Primer Aplicación](#primer-aplicación)
    - [Diferencias entre CRA y Vite](#diferencias-entre-cra-y-vite)
      - [create-react-app](#create-react-app)
      - [Vite](#vite)
    - [Ejecutar la Aplicación](#ejecutar-la-aplicación)
    - [Modificar desde CERO](#modificar-desde-cero)
  - [AGREGAR CSS](#agregar-css)
  - [PROPS](#props)
    - [propTypes](#proptypes)
    - [defaultProps](#defaultprops)
  - [EVENTOS](#eventos)
    - [evento click](#evento-click)
  - [HOOKS](#hooks)
    - [useState](#usestate)
  - [PRUEBAS](#pruebas)
    - [AAA](#aaa)
    - [Pruebas Unitarias](#pruebas-unitarias)
    - [Pruebas de Integración](#pruebas-de-integración)
    - [Instalación de Jest](#instalación-de-jest)
    - [Primer Prueba](#primer-prueba)
  - [PROYECTO GifExpertApp](#proyecto-gifexpertapp)
    - [Instalación](#instalación)
    - [Archivo styles.css](#archivo-stylescss)
    - [Probando APP](#probando-app)
    - [Acceder a GIPHY](#acceder-a-giphy)
    - [Agregar otro componente (AddCategory)](#agregar-otro-componente-addcategory)



## INTRODUCCION

* Manten actualizado Node:

> curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

> REINICIA LA TERMINAL !!!

> Instala la version de Node deseada: nvm install 14.4.0.
> Cambia la version: nvm use --delete-prefix v20.18.0
> npm install -g vite

* Si no tenemos yarn:
> npm install -g yarn


### Primer Aplicación

1. Instalar con __Vite__:
> yarn create vite

2. Nos pedira informacion del proyecto. Poner nombre y en React con JS.
3. Entrar a la __CARPETA DEL PROYECTO__ y abrirla en VSC

> OBSERVACION: Ambos crean un proyecto tipo __NODE__

* Si nos manda error:
> Instalar __DEPENDENCIAS__ con: yarn install



### Diferencias entre CRA y Vite

* Usar __CRA__ para proyectos sencillos
* Usar __Vite__ para proyectos PROFESIONALES
* Usar __npm__ para dependencias GLOBALES
* Usar __yarn__ para dependencias LOCALES


#### create-react-app

1. Crea un __package-lock.json__ que nos dice como se originó el proyecto.
2. __.gitignore__ para indicar lo que no queremos que se suba a GIT o Github
3. __package.json__ con info del proyecto, scripts y dependencias
> Por ejemplo, tenemos los scripts para levantar el servidor de desarrollo,
> construye la version de producción con tree-shaking, pruebas, etc.
4. __README.md__ lo que queremos mostrar en Github, Bitbucket, etc.
5. __PODEMOS VISUALIZARLO CON VSC__ como Markdown: Open Preview
6. La carpeta __node_modules__ de las cuales casi ninguna llega a __PRODUCCIÓN__
7. En public nos encontramos con el __manifest.json__ que es para una __PWA__
8. En __index.html__ es donde se montará la Single Page Application

* __LOS ARCHIVOS .lock NO SE MANIPULAN!__

#### Vite

* __TIENE MENOS DEPENDENCIAS__
* __ES MEJOR EL HOT RELOAD__
* El index.html esta en raíz
* No tiene un robots.txt
* No tiene un manifest.json
* INLUYE un vite.config.js
* Utiliza archivos .jsx

### Ejecutar la Aplicación

> yarn dev

* Si marca errores, instalar dependencias:

> npm install

### Modificar desde CERO

> Ya que vimos que funciona, borrar todo en __src__
> Crear nuestro main.jsx y agregar:

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function App(){
  return(<h1>Hola mundo</h1>)
}

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App/>
  </React.StrictMode>
)
```

> __NO PODEMOS REGRESAR UN OBJETO__

> Para regresar un objeto, usamos:

```javascript
const miObjeto = {
  nombre: 'Fernando'
}
JSON.stringify(miObjeto);
```

## AGREGAR CSS

* Creamos nuestro archivo _style.css_

```css
html, body{
  background-color: #21232A;
  color: white;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 1.3rem;
  padding: 70px;
}
```
* Lo agregamos a nuestro componente:

```jsx
import './style.css'
```

## PROPS

> Se usan para crear __COMUNICACIÓN__ entre componentes
> Normalmente no las trabajamos directamente
> __Desestructuramos cada valor__

```jsx
export const FirstApp = ({title, subTitle}) =>{
  return(
    <>
      <h1>{title}</h1>
      <h2>{subTitle}</h2>
    </>
  )
}
```
> Le pasamos los valores por medio del componente:

```jsx
<FirstApp title="Hola, como estas", subTitle="...esto es un subititulo"/>
```


### propTypes

* __YA Instalado con CRA__
* __Se debe INSTALAR con Vite__
> yarn add prop-types

Importamos la libreria:

```jsx
import PropTypes from 'prop-types';
```

> Al final del componente agregar:

```jsx
App.propTypes = {
  title: PropTypes.string.isRequired,
  subTitle: PropTypes.string
}
```

### defaultProps

```jsx
App.defaultProps = {
  title: 'No hay titulo',
  subTitle: 'No hay subtitulo',
  // Podemos agregar props
  name: 'Fernando'
}
```

## EVENTOS

### evento click

* Se maneja con la palabra __onClick__
* Se recomienda __SEPARAR__ la función
> Si __UNICAMENTE__ recibimos y usamos el evento
> __NO ES NECESARIO PONERLO__

```jsx
  function add(e){
    console.log(e);
  }

  return(
    <>
      <h1>CounterApp</h1>
      <button onClick={add}>
        +1
      </button>
    </>
  )
```

## HOOKS

> __SON FUNCIONES__
> Comienzan con la palabra __use__

### useState

```jsx
import {useState} from 'react';

export function CounterApp(){

  const [contador, setContador] = useState(0);

  const add = ()=>{
    setContador(jfk=>jfk+1);
  }
  
  return(
    <>
      <h1>CounterApp <span>{contador}</span></h1>
      <button onClick={add}>
        +1
      </button>
    </>
  )
}
```


## PRUEBAS

> AL MENOS DEBEMOS HACER PRUEBA DE LA __RUTA CRÍTICA__

### AAA

* Arrange (__ARREGLAR__)
> Preparamos el ambiente (__Sujeto de Pruebas__)
> Inicializamos variables
> Hacemos las importaciones necesarias

* Act (__ACTUAR__)
> Aplicamos el __estímulo__
> Llamamos métodos
> Simulamos clicks
> Realizamos acciones

* Assert (__AFIRMAR__)
> __OBSERVAR EL COMPORTAMIENTO RESULTANTE__
> Vemos que algo suceda o no, como es esperado

1. Pueden salir errores a pesar de las pruebas
2. Se ejecutan SOLO en el ambiente de desarrollo
3. Pueden dar falsos (positivos o negativos)
4. Son necesarias


### Pruebas Unitarias
> Enfocada a pequeñas funcionalidades

### Pruebas de Integración
> Enfocadas a cómo reaccionan varias piezas en conjunto


### Instalación de Jest
> yarn add --dev jest

* Agregar en nuestro package.json

```json
{
  "scripts":{
    "test": "jest"
  }
}
```

### Primer Prueba

* Ejecutamos con:
> yarn test

1. __SE RECOMIENDA TENER UNA CARPETA "tests"__
2. Ahi tendríamos una copia de todo nuestro proyecto en versión __"test"__
3. Al menos debemos tener un archivo con extensión __".test.jsx"__ 
4. Agregar como mínimo:

```jsx
test('Esto no puede fallar',()=>{

})
```

* Instalamos:
> yarn add -D @types/jest

* Ahora agregamos una prueba:

```jsx
describe('PRUEBA PARA COMPONENTE <App/>',()=>{
    test('Esto no falla',()=>{
        const mensaje1 = 'Hola mundo';
        const mensaje2 = mensaje1.trim();
    
        expect(mensaje1).toBe(mensaje2);
    })
})
```

* Nos ayuda mucho tener las __"types"__:
> yarn add -D @types/jest

* __NO PODEMOS HACER PRUEBAS DE ALGO QUE NO TENEMOS EXPORTADO__

> Para trabajar con .then, usamos el **done**


## PROYECTO GifExpertApp

### Instalación

> yarn create vite

1. Eliminar archivos de **src**, solo dejar *main.jsx*
2. Agregar *GifExpertApp.jsx*

- [x] __NO ES NECESARIO IMPORTAR REACT EN CADA ARCHIVO A PARTIR DE LA VERSIÓN 17__
- [x] __NO TENEMOS LOS MÓDULOS DE NODE, HAY QUE IMPORTARLOS!__

> yarn install

- [x] Incluso funciona con solo: 

> yarn

3. Crear el componente GifExpertApp dentro del archivo del mismo nombre
4. Lo importamos y agregamos en el **main**
5. Agregar archivo styles.css

### Archivo styles.css

```css
* {
  font-family: Helvetica, Arial, sans-serif;
  background-color: rgb(234, 234, 234);
}

body {
  padding: 60px;
}

input {
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgb(97, 32, 158);
  color: black;
  font-size: 1.2rem;
  outline: none;
  padding: 10px 15px;
  width: 100%;
}

h2 {
  font-size: 1.5rem;
}

h3 {
  font-size: 3rem;
  margin-bottom: 5px;
}

.card-grid {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  align-content: center;
  align-items: center;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.03);
  display: flex;
  flex-direction: column;
  height: 0%;  
  justify-content: center;
  margin-bottom: 20px;
  margin-right: 20px;
  overflow: hidden;
}

.card p {
  background-color: white;
  flex: 1;
  font-size: 1.5rem;
  margin-top: 5px;
  padding: 5px 20px 0px 20px;
  text-align: center;
}

.card img {
  width: 100%;
}
```
1. Agregar a main.jsx
> import './styles.css'

```jsx
import {useState} from 'react';

export const GifExpertApp = ()=>{
  const [categories, setCategories] = useState(['One Punch', 'Dragon Ball']);

  return(
    <>
      {/* titulo */}
      <h1>GifExpertApp</h1>

      {/* input */}
      

      {/* listado de gifs */}
      <ol>
        {
          categories.map(category=>{
            return <li key={category}>{category}</li>
          })
        }
      </ol>
    </>
  )
}
```

### Probando APP

5. Probar componente ejecutando:
> yarn dev
- [x] Si la primera vez marca **ERROR** instalar dependencias:
> npm install

### Acceder a GIPHY

1. Crear cuenta y loguearnos en: https://developers.giphy.com/
2. Crear nuevo proyecto **API**
3. Copiar la **API Key** 

### Agregar otro componente (AddCategory)

1. Creamos una carpeta components dentro de **src**
2. Agregamos nuestro archivo **AddCategory.jsx**

- [x] DEBEMOS USAR onChange PARA RECIBIR VALORES DE UN INPUT

```jsx
import {useState} from 'react';

export const AddCategory = ()=>{

  const [inputValue, setInputValue] = useState('');

  return(
    <input
      type="text"
      placeholder="Buscar GIFs"
      value={inputvalue}
    >
  )
}
```












