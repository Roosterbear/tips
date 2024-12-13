# Master NodeJS

- [Master NodeJS](#master-nodejs)
  - [Introducción](#introducción)
  - [Módulos](#módulos)
  - [FileSystem](#filesystem)

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

```javascript
const fs = require('fs')
fs.readFile('note.txt',(err,data)=>{
  if(err){
    console.log('Se ha lanbzado el error: ',err)
  }else{
    console.log(data.toString())
  }
})
```








