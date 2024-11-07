# REACT + TYPESCRIPT CON 10 PROYECTOS 57 Hrs.

## Object Literal

```javascript
const nuevo = {
  autenticado,
  usuario
}
```

## Short Circuit

```javascript
const auth = true
auth && console.log('Usuario Autenticado')
```

## Modulos

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


## Fetch API con Promises

```javascript
const url = 'https://jsonplaceholder.typicode.com/comments'

fetch(url)
  .then((response)=>{
    return response.json()
  })
  .then(data=>{
    console.log(data)
  })
```


```javascript

```














































