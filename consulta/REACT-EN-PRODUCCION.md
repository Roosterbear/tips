# REACT v17 en Producción

## INSTALACIONES

> Crear proyecto en REACT
> Instalarle REACT Router
> yarn add react-router-dom@6

## APLICACION

### Principal

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

### Componente

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

## SPA - Single Page Application

> Si revisamos el HTML que nos entrega REACT
> veremos que casi no hay información
> eso es un problema para el SEO

### LAZY

> La IMPORTACION LAZY
> Va carganto los elementos como se vayan necesitando

```jsx
import React, { lazy } from 'rect';
const Home = lazy(()=> import("./pages/home")) 
const About = lazy(()=> import("./pages/about")) 
```


### SUSPENSE

> Sedeben suspender los elementos para usar LAZY 

```jsx
<Route 
  element={<Suspense fallback={<h3>Loading...</h3>}>
    <Home />
  </ Suspense>} path="/" />
```

> Fallback toma un codigo JSX para mostrar 
> mientras está suspendido el elemento


### HELMET

> Agregamos a nuestro proyecto:
> yarn add react-helmet
> Agregamos a nuestra page de Home:
 
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


### SNAP

> Activa SEO

1. Instalar:

> yarn add --dev react-snap

2. Modificar __package.json__ 

> Agregamos el script después del build:

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

> yarn build

## Netlify

1. Crear cuenta
2. Add new site
3. Deploy manually
4. Subir carpeta build













