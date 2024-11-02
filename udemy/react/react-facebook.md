# REACT - LA BIBLIOTECA JS CREADA POR FACEBOOK 2.5 Hrs.

## INTRODUCCION

### YARN

> Instalar yarn
> Nos sirve para instalar paquetes:
> yarn add react-toastify
> yarn remove react-toastify

### JSX

> Mezcla Javascript con HTML


### Virtual DOM

> Se actualiza por componente y sus hijos


### Primer Aplicación

> npm install -g create-react-app
> npx create-react-app first-app
> Entrar a la carpeta y ejecutar: yarn start


### Estructura

* node_modules

> Contiene todas las dependencias
> No es necesario compartirla

* public

> Archivos estáticos básicos del proyecto

* src

> Nuestro proyecto con el que trabajamos

1. __App.js__ - Es nuestro primer nodo de la Aplicación


* package.json

> Contiene la configuración del proyecto
> Incluye la lista para bajar dependencias
> Scripts: nombres cortos de scripts del proyecto



## PRIMERA APP


### --- BUENAS PRACTICA ---

> Crear una carpeta "__components__"
> Crear componente, comenzando en __MAYUSCULAS__
> Llamar igual al archivo como al componente
> Debemos crear funciones, y pueden ser:

* HolaMundo.js

```jsx
import React from 'react';

export default function HolaMundo(){
  return(
    <div>
      <h1>Hola Mundo</h1>
      <h2>Roosterbear</h2>
    </div>
  );
}
```
* HolaMundo.js

```jsx
import React from 'react';

const HolaMundo = ()=>{
  return(
    <div>
      <h1>Hola Mundo</h1>
      <h2>Roosterbear</h2>
    </div>
  )
}

export default HolaMundo;
```

> Ahora debemos IMPORTAR nuestro componente:
> import HolaMundo from './components/HolaMundo'

> Podemos crear más componentes en un archivo, pero:
> Solo puede existir __UN COMPONENTE DEFAULT__ por archivo

* 

> __PARA AGREGAR COMPONENTES QUE NO SON DEFAULT__: ->
> Envolvemos el componente entre llaves: __{SegundoComponente}__

> Un componente SOLO devuelve __UN ELEMENTO__
> Si no queremos un elemento principal, envolvemos en un __FRAGMENT__:

```jsx
<>
  <h1>Hola Mundo</h1>
  <h2>Roosterbear</h2>
</>
```
> Si queremos tener FUNCIONES, las ponemos ANTES del __RETURN__


## PROPS


```jsx
import React from 'react';

export defaul function Saludar(props){
  console.log(props);

  return(
    <div>
      <h2>Hola Roosterbear</h2>
    </div>
  );
}
```
> En nuestra aplicación principal, importamos y agregamos el componente:

```jsx
import Saludar from './components/Saludar'

<Saludar />
```

### PASAR UN OBJETO A UN COMPONENTE POR PROPS

> App.js

```jsx
import './App.css';
import Saludo from './components/Saludo'

function App() {
  const user = {
    name:"Luis Fernando",
    edad:48,
    library:"React",
    so:"Linux",
    language:"Go"
  }

  return (
    <>      
      <Saludo userInfo={user}/>
    </>
  );
}
export default App;
```
> Saludo.js

```jsx
import React from 'react'

export default function Saludo(props){
  return(
    <>
      <h1>Soy {props.userInfo.name}</h1>
      <h2>tengo {props.userInfo.edad} años</h2>
      <h3>{`y me gusta usar 
        ${props.userInfo.so} y programar en 
        ${props.userInfo.language} y
        ${props.userInfo.library}`}
      </h3>
    </>
  );
}
```

### PASANDO FUNCIONES ENTRE COMPONENTES POR PROPS

> App.js

```jsx
import './App.css';
import Saludar from './components/Saludar'

function App() {
  const user = {
    name:"Luis Fernando"
  }

  const saludarFn = name=>{
    console.log("Hola "+name);
  }

  return (
    <>      
      <Saludar userInfo={user} saludarFn={saludarFn}/>
    </>
  );
}
export default App;
```

> Saludar

```jsx
import React from 'react'

export default function Saludar(props){
  return(
    <>
      <button onClick={()=>props.saludarFn(props.userInfo.name)}>
      Saludar
      </button>
    </>
  );
}
```
> Necesitamos agregar la FUNCIÓN DE FLECHA para que
> NO se ejecute la función de manera automática
















