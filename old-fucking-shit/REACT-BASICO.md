
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
      /* Necesitamos agregar la FUNCIÓN DE FLECHA para que */
      /* NO se ejecute la función de manera automática */
      <button onClick={()=>props.saludarFn(props.userInfo.name)}>
      Saludar
      </button>
    </>
  );
}
```

### DESTRUCTURING

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
      /* AHORA YA NO NECESITAMOS AGREGAR props */
      /* Y TAMPOCO NECESITAMOS YA AGREGAR userInfo */
      <button onClick={()=>saludarFn(name)}>
      Saludar
      </button>
    </>
  );
}
```


### AGREGANDO BOOTSTRAP

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


### SVG

> Movemos la imagen __SVG__ a una carpeta [assets]

> Importamos:

```jsx
import {reactComponent as ReactIcon} from "./assets/react.svg";

/* Lo importamos como cualquier componente */

<ReactIcon />

/* RECUERDA QUE DEBEMOS DARLE ESTILO AL COMPONENTE */
```

## HOOKS

### useState

> Nos permiten manejar los __ESTADOS__ de los COMPONENTES

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

































