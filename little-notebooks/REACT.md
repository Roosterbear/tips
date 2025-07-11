<h1 style="color:#2a9d8f">REACT</h1>

- [REACT](#react)
  - [INTRODUCCIÓN](#introducción)
    - [Mantener actualizado Node](#mantener-actualizado-node)
  - [YARN](#yarn)
  - [PRIMER PROYECTO](#primer-proyecto)
    - [Creación](#creación)
    - [Ejecución](#ejecución)
    - [Primer código](#primer-código)
    - [Agregar CSS](#agregar-css)
    - [Agregando BOOTSTRAP](#agregando-bootstrap)
    - [Mejorando la Vista](#mejorando-la-vista)
    - [Buenas prácticas](#buenas-prácticas)
    - [Recorrer un Array](#recorrer-un-array)
  - [PROPS](#props)
    - [Pasar un Objeto a un Componente por PROPS](#pasar-un-objeto-a-un-componente-por-props)
    - [Pasando Funciones entre Componentes por PROPS](#pasando-funciones-entre-componentes-por-props)
    - [Destructuring](#destructuring)
    - [propTypes](#proptypes)
    - [defaultProps](#defaultprops)
  - [EVENTOS](#eventos)
    - [evento click](#evento-click)
  - [HOOKS](#hooks)
    - [useState](#usestate)
    - [Manejar el ESTADO con valores Booleanos](#manejar-el-estado-con-valores-booleanos)
    - [Otro ejemplo de useState](#otro-ejemplo-de-usestate)
    - [useEffect](#useeffect)
  - [React ROUTER](#react-router)
  - [REACT en Producción](#react-en-producción)
    - [Principal Código Ejemplo](#principal-código-ejemplo)
    - [Componente Código Ejemplo](#componente-código-ejemplo)
    - [Agregar LAZY](#agregar-lazy)
    - [Agregar SUSPENSE](#agregar-suspense)
    - [Agregar HELMET](#agregar-helmet)
    - [Agregar SNAP](#agregar-snap)
    - [Netlify](#netlify)
    - [Desplegar en Github Pages](#desplegar-en-github-pages)
    - [ARCHIVOS BARRIL](#archivos-barril)
- [REACT NATIVE](#react-native)

## INTRODUCCIÓN

* Es una librería
* Si queremos cosas más complejas, agregamos más librerías
* Ideal para páginas privadas

> Debemos tener instalado:

- [x] Node / NPM
- [x] Yarn  
- [x] Vite

```bash
npm install -g vite
npm install -g yarn
```

> Opcionalmente podemos usar __bun__ ```curl https://bun.sh/install | bash```

- [x] Instalar React con bun: ```bun create react-app proyecto```


### Mantener actualizado Node

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```
- [x] Reiniciar terminal
- [x] Instala la version de Node deseada:

```bash
nvm install 14.4.0.
```

## YARN

> Nos sirve para manejar paquetes

```bash
yarn add react-toastify
yarn remove react-toastify
```

## PRIMER PROYECTO

### Creación

```bash
yarn create vite
```

- [x] Si nos manda error, instalar dependencias:

```bash
yarn install
```

### Ejecución

- [x] Entrar a carpeta de proyecto

```bash
yarn dev
```
- [x] Si marca error:

```bash
npm install
```

### Primer código

- [x] Ya que vimos que funciona, borrar todo en __src__
- [x] Crear nuestro **main.jsx** y agregar:

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

### Agregar CSS

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

### Agregando BOOTSTRAP

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

### Mejorando la Vista

> Instalamos: npm install react-icons --save
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

### Buenas prácticas

- [x] Crear una carpeta **"components"**
- [x] Usar mismo nombre para **archivo** y **componente**
- [x] Nombrar componente iniciando en **mayúscula**

### Recorrer un Array

- [x] Después de la función flecha no necesitamos llaves
- [x] Podríamos agregar paréntesis

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

## PROPS

> Se usan para crear __COMUNICACIÓN__ entre componentes

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

### Pasar un Objeto a un Componente por PROPS

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

### Pasando Funciones entre Componentes por PROPS

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

### Destructuring

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

### propTypes

- [x] __YA Instalado con CRA__
- [ ] __Se debe INSTALAR con Vite__

```bash
yarn add prop-types
```

- [x] Importamos la libreria:

```jsx
import PropTypes from 'prop-types';
```

- [x] Al final del componente agregar:

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


## HOOKS

- [x] __SON FUNCIONES__
- [x] Comienzan con la palabra __use__

### useState

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

### useEffect

> Se ejecuta cuando el componente YA HA SIDO MONTADO

```jsx
import React, {useState, useEffect} from "react";

export default function App(){
  const [stateCar, setStateCar] = useState(false);
  const [contar, setContar] = useState(0);

  useEffect(()=>{
    console.log("Total: "+contar);
    /* AQUI PONEMOS LAS VARIABLES A ACTUALIZAR */
  }, [contar]);

  const encenderApagar = ()=>{
    /* ESTA PARTE ES INTERESANTE PORQUE TE REGRESA LO CONTRARIO DEL ESTADO ACTUAL ! */
    setStateCar(!stateCar);
  };

  return(
    <div>
      <h3>El coche esta {stateCar ? "Encendido":"Apagado"}</h3>
      <h4>Click: {contar}</h4>
      <button onClick={encenderApagar}>Encender / Apagar</button>
    </div>
  )
}
```

## React ROUTER

> Instalamos: npm install react-router-dom

> Importamos:

```jsx
import {BrowserRouter as Router, Switch, Route, Link} from 'react-router-dom';
```

> Creamos una carpeta llamada "pages"
> Dentro de ella creamos dos archivos de componentes: contacto.js y acerca.js
> Importamos nuestras páginas:
> Agregamos nuestras rutas:

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


## REACT en Producción

- [x] Crear proyecto en REACT
- [x] Instalarle REACT Router

```bash
yarn add react-router-dom@6
```

### Principal Código Ejemplo

```jsx
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import NavBar from './components/NavBar';
import Home from './pages/Home';
import About from './pages/About';

const App = ()=>{
  return (
    <BrowserRouter>
      <NavBar />
      <Routes>
        <Route element={<Home />} path="/" />
        <Route element={<About/>} path="about" />
      </Routes>
    </BrowserRouter>
  );
};

export default App;
```

### Componente Código Ejemplo

```jsx
import React from 'rect';
import { Link } from 'react-router-dom';

const NavBar = ()=>{
  return <nav>
    <link to="">Home </link>
    <link to="about">About </link>
  </nav>
};

export default NavBar;
```

### Agregar LAZY

> La importación LAZY va cargando los elementos como se vayan necesitando

- [x] Modificamos nuestro main.jsx

```jsx
import React, { lazy } from 'rect';
const Home = lazy(()=> import("./pages/home")) 
const About = lazy(()=> import("./pages/about")) 
```

### Agregar SUSPENSE

> Se deben suspender los elementos para usar LAZY 

```jsx
<Route 
  element={<Suspense fallback={<h3>Loading...</h3>}>
    <Home />
  </ Suspense>} path="/" />
```

> Fallback toma un codigo JSX para mostrar 
> mientras está suspendido el elemento


### Agregar HELMET

- [x] Agregamos a nuestro proyecto:

```bash
yarn add react-helmet
```
- [x] Agregamos a nuestra page de Home:

```jsx
import React from 'react';
import { helmet } from 'react-helmet';

const Home = ()=>{
  return(
    <div>
      <Helmet title="Mi Pagina - Home" />
      <h1>Home page</h1>
    </div>
  )
};

export default Home;
```

### Agregar SNAP

> Activa SEO

- [x] Instalar:

```bash
yarn add --dev react-snap
```

- [x] Modificar __package.json__ 
- [x] Agregamos el script después del build:

```json
"postbuild": "react-snap",
```

```jsx
import Reacr from 'react';
import { render, hydrate } from react-dom;
import "./index.css";
import App from "./App";
import reportWebVitals from './reportWebVitals';

const rootElement = document.getElementById("root");

if (rootElement.hasChildNodes()){
  hydrate(<App />, rootElement);
}else{
  render(<App />, rootElement);
}

reportWebVitals();
```

> Agregar en el package.json despues de los scripts

```json
"reactSnap": {
  "source":"build",
  "miniyHtml":{
    "collapseWhitespace":false,
    "removeComments":false
  }
},
```
- [x] Construir

```bash
yarn build
```
<div style="color:#ff004d";>

### Netlify
</div>

1. Crear cuenta
2. Add new site
3. > yarn build
4. Subir carpeta dist


### Desplegar en Github Pages

> En React terminamos con un producto final que son archivos HTML, CSS y Javascript

* Renombrar dist a __docs__
* Subir a Github
* Settings - Pages
* Seleccionar __main__
* Seleccionar __docs__
* Esperar hasta que esté en VERDE, dar F5 constantemente

<br/>
🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥

> CUIDAR DE TENER LOS ENLACES TIPO: './carpeta'

🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥

<br/>

### ARCHIVOS BARRIL

> En la carpeta components agregar un _index.js_ con nuestras exportaciones:

```jsx
export * from './Componente1';
export * from './Componente2';
export * from './Componente3';
```

> Tan solo importamos:

```jsx
import {Componente1, Componente2, Componente3} from './components' // NO es necesario agregar index.js
```

# REACT NATIVE

```bash
npx create-expo-app@latest --template blank-typescript
cd proyecto
npm start
```





