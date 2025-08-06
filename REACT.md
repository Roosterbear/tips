<h1 style="color:#2a9d8f">REACT</h1>

- [INTRODUCCIÓN](#introducción)
  - [Agregar CSS](#agregar-css)
  - [Agregando BOOTSTRAP](#agregando-bootstrap)
  - [Mejorando la Vista](#mejorando-la-vista)
- [BUENAS PRÁCTICAS](#buenas-prácticas)
  - [Barriles](#barriles)
- [Javascript en React](#javascript-en-react)
  - [Spread Operator](#spread-operator)
  - [Template String \`](#template-string-)
  - [Destructuring](#destructuring)
  - [Evaluación CORTO-CIRCUITO](#evaluación-corto-circuito)
- [PROPS](#props)
  - [Pasar un Objeto a un Componente por PROPS](#pasar-un-objeto-a-un-componente-por-props)
  - [Pasando Funciones entre Componentes por PROPS](#pasando-funciones-entre-componentes-por-props)
  - [Destructuring](#destructuring-1)
- [EVENTOS](#eventos)
  - [evento click](#evento-click)
- [HOOKS](#hooks)
  - [useState](#usestate)
    - [Manejar el ESTADO con valores Booleanos](#manejar-el-estado-con-valores-booleanos)
    - [Otro ejemplo de useState](#otro-ejemplo-de-usestate)
  - [useEffect](#useeffect)
- [React ROUTER](#react-router)

# INTRODUCCIÓN

```bash
npm create vite@latest
```

## Agregar CSS

- [x] Creamos nuestro archivo _style.css_

```css
html, body{
  background-color: #21232A;
  color: white;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 1.3rem;
  padding: 70px;
}
```
- [x] Lo agregamos a nuestro componente:

```jsx
import './style.css'
```

## Agregando BOOTSTRAP

> Instalamos: npm install react-bootstrap bootstrap

> Importamos boostrap en el index.js:

```jsx
import "bootstrap/dist/css/bootstrap.min.css";
```

> Ahora agregamos en un componente:

```jsx
import {Button} from 'react-bootstrap';
```

> Agregamos un botón:

```jsx
<Button variant="primary">Enviar</Button>
```

## Mejorando la Vista

> Instalamos: ```npm install react-icons --save```
> Importamos:

```jsx
import React, {Component} from 'react'
import {IoIosStar, IoIosStarOutline} from 'react-icons/io'

class Rating extends Component{
  render(){
    return(
      <>
        <IoIosStar/>
        <IoIosStarOutline/>
      </>
    )
  }
}
```

# BUENAS PRÁCTICAS

- [x] Crear una carpeta **"components"**
- [x] Usar mismo nombre para **archivo** y **componente**
- [x] Nombrar componente iniciando en **mayúscula**

## Barriles

> En la carpeta __components__ agregar un _index.js_ con nuestras exportaciones:

```jsx
export * from './Componente1';
export * from './Componente2';
export * from './Componente3';
```

> Tan solo importamos:

```jsx
import {Componente1, Componente2, Componente3} from './components' // NO es necesario agregar index.js
```

- [x] En components, creamos una carpeta para cada componente con su index correspondiente

```jsx
export * from './Button1/Button.tsx';
export * from './Button2/Button.tsx';
```

```jsx
import {Button1, Button2} from './components' // Y listo !!
```

# Javascript en React

```jsx
function App() {
  
  const languages = ["Go", "Javascript", "Ruby", "Java"]
  
  return (
    <div className="App">
      <ul>
      {
        languages.map((num, index)=>
        <li key={index}>{num}</li>)
      }
      </ul>
    </div>  
  );
}
```

## Spread Operator

- [x] NO es buena práctica seguir usando __push__ para agregar elementos

```setArreglo([...arreglo], {nombre: 'nuevo valor', visto: false})```


## Template String `

- [x] Es mejor práctica para __CONCATENAR__

```javascript
const hola = "Hola";
const mundo = "mundo";

console.log(`${hola} ${mundo}`);
```

## Destructuring

```javascript
const producto = {nombre:"Laptop", precio: 2000, disponible: true}
const cliente = {nombre:"Fernando", premium: true}

// Asignamos una variable para cada campo del objeto
const {nombre, precio, disponible} = producto

// Tenemos un conflicto, hay 2 nombres, pero lo podemos renombrar:
const {nombre: nombreCliente, premium} = cliente
```

## Evaluación CORTO-CIRCUITO

- [x] Es para evaluaciones "__Truthy__"
- [x] Sustituye a un __if__
- [x] En caso de verdadero, regresa lo de la __derecha__

```javascript
const auth = true;
auth && console.log('Usuario autenticado');
```

# PROPS

> Se usan para crear __COMUNICACIÓN__ entre componentes

```jsx
import React from 'react';

export default function Saludar(props){
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

## Pasar un Objeto a un Componente por PROPS

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

- [x] NO PODEMOS REGRESAR UN OBJETO

> Para regresar un objeto, usamos:

```javascript
const miObjeto = {
  nombre: 'Fernando'
}
JSON.stringify(miObjeto);
```

## Pasando Funciones entre Componentes por PROPS

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
      /* Necesitamos agregar la FUNCIÓN DE FLECHA para que */
      /* NO se ejecute la función de manera automática */
      <button onClick={()=>props.saludarFn(props.userInfo.name)}>
      Saludar
      </button>
    </>
  );
}
```

## Destructuring

> Normalmente NO trabajamos las PROPS directamente
> __Desestructuramos cada valor__


```jsx
import React from 'react'

export default function Saludar(props){
  /* SEPARAMOS LAS CONSTANTES QUE LLEGAN DE props */
  const {userInfo, saludarFn} = props;
  /* AHORA SEPARAMOS EL nombre DE userInfo */
  /* ------------------------------------- */
  /* DAMOS UN VALOR POR DEFAULT */
  const {nombre = "Sin usuario"} = userInfo;
  
  return(
    <>
      {/* AHORA YA NO NECESITAMOS AGREGAR LA PALABRA props */}
      {/* Y TAMPOCO NECESITAMOS YA AGREGAR userInfo */}
      <button onClick={()=>saludarFn(name)}>
      Saludar
      </button>
    </>
  );
}
```

# EVENTOS

## evento click

- [x] Se maneja con la palabra __onClick__
- [x] Se recomienda __SEPARAR__ la función
- [x] Si __UNICAMENTE__ recibimos y usamos el evento __NO ES NECESARIO PONERLO__

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
# HOOKS

## useState

- [x] Nos permiten manejar los __ESTADOS__ de los COMPONENTES

> Para usar el Hook __useState__ hacemos lo siguiente:

1. Importamos:

```jsx
import React, {useState} from 'react';
```

2. Creamos un array con 2 elementos:

```jsx
import React, {useState} from 'react';

export default function Ejemplo(){

  /* Un elemento es el valor del estado y el otro la función que lo actualiza */
  const [count, setCount] = useState(0);
  return(
    <div>
      <p>You clicked me {count} times </p>
      <button onClick={()=>setCount(count+1)}>
    </div>
  );
}
```

### Manejar el ESTADO con valores Booleanos

```jsx
import React, {useState} from "react";

export default function App(){
  const [stateCar, setStateCar] = useState(false);

  const encenderApagar = ()=>{
    /* ESTA PARTE ES INTERESANTE PORQUE TE REGRESA LO CONTRARIO DEL ESTADO ACTUAL ! */
    setStateCar(!stateCar);
  };

  return(
    <div>
      <h3>El coche esta {stateCar ? "Encendido":"Apagado"}</h3>
      <button onClick={encenderApagar}>Encender / Apagar</button>
    </div>
  )
}
```

### Otro ejemplo de useState

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

## useEffect

- [x] Se ejecuta cuando el componente __YA HA SIDO MONTADO__
- [x] __USAR__ para eventos __EXTERNOS__
- [x] No es buena práctica para eventos del mismo componente


```jsx
  useEffect(()=>{
    // Esto se ejecuta al montarse el componente
    // Y también cuando cambia el ESTADO
  });
```

```jsx
  useEffect(()=>{
    // Esto se ejecuta SOLO al montarse el componente
  },[]);
    // El solo poner [] hace que no se ejecute cuando cambia el estado
```

```jsx
  useEffect(()=>{
    // Esto se ejecuta SOLO al montarse el componente
  },[counter]);
    // Se ejecuta de nuevo cuando cambia el ESTADO de counter
```

* App.js

```jsx
import { useState } from "react";
import Child from "./components/Child";

function App(){
  const [showChild, setShowChild] = useState(true);
  return(
    <div>
      <h1>useEffect</h1>
      <button onClick={()=>setShowChild(!showChild)}>Toggle Child</button>
      {showChild && <Child></Child>}
    </div>
  );
}
export default App;
```

* components/Child.js

```jsx
import { useEffect, useState } from "react";

function Child(){
  const [counter, setCounter] = useState(0);

  useEffect(()=>{
    return ()=>{ // Con este RETURN desmontamos el useEffect
      console.log("El componente se ha desmontado")
    }
  },[]);

  return(
    <div className="child">
      <h2>Componente Hijo</h2>
      <h3>{counter}</h3>
      <button onClick={()=>setCounter(counter++)}>+</button>
    </div>
  );
}
export default Child;
```

# React ROUTER

- [x] Instalamos: npm install react-router-dom

> Importamos:

```jsx
import {BrowserRouter as Router, Switch, Route, Link} from 'react-router-dom';
```

1. Creamos una carpeta llamada "pages"
2. Dentro de ella creamos dos archivos de componentes: contacto.js y acerca.js
3. Importamos nuestras páginas:
4. Agregamos nuestras rutas:

```jsx
import React from 'react';
import {BrowserRouter as Router, Switch, Route, Link} from 'react-router-dom';
import Contacto from './pages/Contacto';
import Acerca from './pages/Acerca';

export default App(){
  return(
    <div>
      <h1>React Router</h1>
      <Router>
        /* PONEMOS NUESTROS LINKS */
        <div>
          <Link to="/">
            <Button>Home</Button>
          </Link>
          <Link to="/contacto">
            <Button>Contacto</Button>
          </Link>
          <Link to="/acerca">
            <Button>Acerca</Button>
          </Link>
        </div>

        /* LAS RUTAS VAN DENTRO DE ROUTER */
        <Switch>          
          <Route path="/contacto">
            <Contacto/>
          </Route>
          <Route path="/acerca">
            <Acerca/>
          </Route>
        </Switch>
      </Router>
    </div>
  );
}
```



