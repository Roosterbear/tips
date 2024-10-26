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

----

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