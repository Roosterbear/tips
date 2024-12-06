# REACT + TYPESCRIPT CON 10 PROYECTOS 57 Hrs.

## REPASO JAVASCRIPT

### Object Literal

```javascript
const nuevo = {
  autenticado,
  usuario
}
```

### Short Circuit

```javascript
const auth = true
auth && console.log('Usuario Autenticado')
```

### Modulos

> funciones.js

```javascript
export function sumar(n1, n2){
  return n1+n2
}

export function restar(n1, n2){
  return n1-n2
}
```

> index.js

```javascript
import {sumar} from './funciones.js'

const resultado = sumar(22,10)
console.log(resultado)
```


### Fetch API con Promises

```javascript
const url = 'https://jsonplaceholder.typicode.com/comments'

fetch(url)
  .then(response=>{
    if(response.ok){
      return response .json()
    }
    throw new Error('Hubo un error')
  })
  .then(data=>{
    console.log(data)
  })
  .catch(error=>{
    console.log(error, message)
  })
```

## PRIMER PROYECTO

> Ejecutamos: npm create vite@latest
> Elegir:

* Nombre del Proyecto
* React
* Javascript + SWC

> Entrar a la __carpeta del proyecto__
> Ejecutar: npm run dev
> Nos manda una dirección para ver el proyecto
> Nos pide modificar para probar el Hot Module Replacement (HMR)



```jsx

```














































