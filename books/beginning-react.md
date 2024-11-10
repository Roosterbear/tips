# BEGINNING REACT

## Trucos

### RECORRER UN ARRAY

- [Google]("www.google.com") - Esto va a Google.

> Después de la función flecha no necesitamos llaves
> Podríamos agregar paréntesis

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

### INSTALAR BOOTSTRAP

> Agregar a nuestro HTML:

```html
<link rel="stylesheet"
href="https://maxcdn.bootstrapcdn.com/bootstrap/latest/css/bootstrap.min.css">
```

> Instalamos: npm install react-bootstrap bootstrap

> Importamos:

```jsx
import React, {Component} from 'react'
import ReactDOM from 'react-dom/client'
import {Button} from 'react-bootstrap'

class App extends Component{
  render(){
    return(
      <div>
        <Button variant="primary">Default</Button>
      </div>
    )
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <App/>
)
```

### MEJORANDO LA VISTA

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

### MEJORES FORMULARIOS CON FORMIK

> Instalamos: npm install formik --save

```jsx
```








































































