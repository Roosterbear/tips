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
    - [Buenas prácticas](#buenas-prácticas)

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


### Buenas prácticas

- [x] Crear una carpeta **"components"**
- [x] Usar mismo nombre para **archivo** y **componente**
- [x] Nombrar componente iniciando en **mayúscula**




















