# REACT

__Menú__

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
  - [PRUEBAS](#pruebas)
    - [AAA](#aaa)
    - [Pruebas Unitarias](#pruebas-unitarias)
    - [Pruebas de Integración](#pruebas-de-integración)
    - [Instalación de Jest](#instalación-de-jest)
    - [Primer Prueba](#primer-prueba)
  - [REACT en Producción](#react-en-producción)
    - [Principal Código Ejemplo](#principal-código-ejemplo)
    - [Componente Código Ejemplo](#componente-código-ejemplo)
    - [Agregar LAZY](#agregar-lazy)
    - [Agregar SUSPENSE](#agregar-suspense)
    - [Agregar HELMET](#agregar-helmet)
    - [Agregar SNAP](#agregar-snap)
  - [Netlify](#netlify)
  - [PROYECTO GifExpertApp](#proyecto-gifexpertapp)
    - [Instalación](#instalación)
    - [Archivo styles.css](#archivo-stylescss)
    - [Recorriendo nuestro array](#recorriendo-nuestro-array)
    - [Viendo cómo va quedando nuestra App](#viendo-cómo-va-quedando-nuestra-app)
    - [Acceder a GIPHY](#acceder-a-giphy)
    - [Agregar otro componente (AddCategory)](#agregar-otro-componente-addcategory)

## INTRODUCCIÓN

> Debemos tener instalado:

- [x] Node / NPM
- [x] Yarn  
- [x] Vite

```bash
npm install -g vite
npm install -g yarn
```

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

- [x] Instalamos:

```bash
yarn add -D @types/jest
```

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

- [x] Nos ayuda mucho tener las __"types"__:

```bash
yarn add -D @types/jest
```

- [ ] __NO PODEMOS HACER PRUEBAS DE ALGO QUE NO TENEMOS EXPORTADO__

- [x] Para trabajar con .then, usamos el **done**


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

> La importación LAZY va carganto los elementos como se vayan necesitando

- [x] Modificamos nuestro main.jsx

```jsx
import React, { lazy } from 'rect';
const Home = lazy(()=> import("./pages/home")) 
const About = lazy(()=> import("./pages/about")) 
```

### Agregar SUSPENSE

> Sedeben suspender los elementos para usar LAZY 

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

## Netlify

1. Crear cuenta
2. Add new site
3. Deploy manually
4. Subir carpeta build




## PROYECTO GifExpertApp

### Instalación

```bash
yarn create vite
```

1. Eliminar archivos de **src**, solo dejar *main.jsx*
2. Agregar *GifExpertApp.jsx*

- [x] __NO ES NECESARIO IMPORTAR REACT EN CADA ARCHIVO A PARTIR DE LA VERSIÓN 17__
- [ ] __NO TENEMOS LOS MÓDULOS DE NODE, HAY QUE IMPORTARLOS!__

```bash
yarn install
```

- [x] Incluso funciona con solo: 

```bash
yarn
```

1. Crear el componente GifExpertApp dentro del archivo del mismo nombre
2. Lo importamos y agregamos en el **main**
3. Agregar archivo styles.css

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
- [x] Agregar a main.jsx

```jsx
import './styles.css'
```

### Recorriendo nuestro array

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

### Viendo cómo va quedando nuestra App

1. Probar componente ejecutando:

```bash
yarn dev
```
- [x] Si la primera vez marca **ERROR** instalar dependencias:

```bash
npm install
```

### Acceder a GIPHY

1. Crear cuenta y loguearnos en: https://developers.giphy.com/
2. Crear nuevo proyecto **API**
3. Copiar la **API Key** 

### Agregar otro componente (AddCategory)

1. Creamos una carpeta components dentro de **src**
2. Agregamos nuestro archivo **AddCategory.jsx**

- [x] DEBEMOS USAR onChange PARA RECIBIR VALORES DE UN INPUT
- [x] RECIBIMOS event EN EL onChange [**LO PONGAMOS O NO**]
- [x] DEBEMOS USAR *event.target.value* PARA OBTENER EL VALOR DEL INPUT
- [x] PODEMOS DESESTRUCTURAR *event* con **{target}**
- [x] PODEMOS USAR UN FORM TRADICIONAL PARA CREAR UN SUBMIT CON **Enter**

```jsx
import {useState} from 'react';

export const AddCategory = ()=>{

  const [inputValue, setInputValue] = useState('');
  const onInputChange = ()=>{
    setInputValue();
  }


  return(
    <input
      type="text"
      placeholder="Buscar GIFs"
      value={inputvalue}
      onChange={onInputChange}
    >
  )
}
```










































