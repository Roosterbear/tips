# REACT DE CERO A EXPERTO 54 Hrs.

## INTRODUCCION

* Manten actualizado Node:

> curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

> REINICIA LA TERMINAL !!!

> Instala la version de Node deseada: nvm install 14.4.0.
> Cambia la version: nvm use --delete-prefix v20.18.0
> npm install -g vite

* Si no tenemos yarn:
> npm install -g yarn


## PRIMERA APLICACION

1. Instalar con __Vite__:
> yarn create vite

2. Nos pedira informacion del proyecto. Poner nombre y en React con JS.
3. Entrar a la __CARPETA DEL PROYECTO__ y abrirla en VSC

> OBSERVACION: Ambos crean un proyecto tipo __NODE__

* Si nos manda error:
> Instalar __DEPENDENCIAS__ con: yarn install



## DIFERENCIAS ENTRE CRA Y VITE

* Usar __CRA__ para proyectos sencillos
* Usar __Vite__ para proyectos PROFESIONALES
* Usar __npm__ para dependencias GLOBALES
* Usar __yarn__ para dependencias LOCALES


### CREATE-REACT-APP

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

### Vite

* __TIENE MENOS DEPENDENCIAS__
* __ES MEJOR EL HOT RELOAD__
* El index.html esta en raíz
* No tiene un robots.txt
* No tiene un manifest.json
* INLUYE un vite.config.js
* Utiliza archivos .jsx



## EJECUTAR LA APLICACION

> yarn dev

* Si marca errores, instalar dependencias:

> npm install

## MODIFICAR DESDE CERO

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

## props

> Se usan para crear __COMUNICACIÓN__ entre componentes
> Normalmente no las trabajamos directamente
> __Desestructuramos cada valor__

```jsx
export const FirstApp({title, subTitle}) =>{
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


## propTypes

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

## defaultProps

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


### PRUEBAS UNITARIAS
> Enfocada a pequeñas funcionalidades

### PRUEBAS DE INTEGRACIÓN
> Enfocadas a cómo reaccionan varias piezas en conjunto


### INSTALACIÓN
> yarn add --dev jest

* Agregar en nuestro package.json

```json
{
  "scripts":{
    "test": "jest"
  }
}
```

* Ejecutamos con:
> yarn test

* Debemos tener cierta información para que se ejecuten pruebas.

* Instalamos:
> yarn add -D @types/jest















