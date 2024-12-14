# Master NodeJS

- [Master NodeJS](#master-nodejs)
  - [Introducción](#introducción)
  - [Módulos](#módulos)
  - [FileSystem](#filesystem)
    - [Leer un archivo](#leer-un-archivo)
    - [Escribir en un archivo](#escribir-en-un-archivo)
    - [Agregar un archivo](#agregar-un-archivo)
    - [Crear un directorio](#crear-un-directorio)

## Introducción

- [x] Instalar NodeJS
- [x] Crear un directorio para nuestro **proyecto**

```bash
mkdir proyecto
```
- [x] Crear un archivo **app.js** dentro de ese directorio
- [x] Ejecutar un ```console.log('Hola mundo')``` con:

```bash
node app
```

## Módulos

- [x] Crear un archivo que contenga un objeto
- [x] Exportamos con:

```javascript
const users = [
  {
    "id":1,
    "name":"root"
  },
  {
    "id":2,
    "name":"user"
  }
]
const nums = [1,2,3];
module.exports = {users,nums}
```
- [x] Importamos con:

```javascript
const importaciones = require('./users');
```

## FileSystem

### Leer un archivo

```javascript
const fs = require('fs')
fs.readFile('note.txt',(err,data)=>{
  if(err){
    console.log('Se ha lanzado el error: ',err)
  }else{
    console.log(data.toString())
  }
})
```

### Escribir en un archivo

```javascript
const fs = require('fs')
fs.writeFile('note.txt','Un mensaje nuevecito',(err,data)=>{
  if(err){
    console.log('Se ha lanzado el error: ',err)
  }else{
    console.log('Se ha guardado el mensaje')
  }
})
```

### Agregar un archivo

```javascript
const fs = require('fs')
fs.appendFile('note.txt','Un mensaje nuevo \n',(err,data)=>{
  if(err){
    console.log('Se ha lanzado el error: ',err)
  }else{
    console.log('Se ha agregado el mensaje')
  }
})
```

### Crear un directorio









