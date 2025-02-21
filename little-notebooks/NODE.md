<div style="color:#FF6500">

# NodeJS
</div>

- [NodeJS](#nodejs)
  - [Introducción](#introducción)
  - [Módulos](#módulos)
  - [FileSystem](#filesystem)
    - [Leer un archivo](#leer-un-archivo)
    - [Escribir en un archivo](#escribir-en-un-archivo)
    - [Agregar un archivo](#agregar-un-archivo)
    - [Crear un directorio](#crear-un-directorio)
    - [Leer archivo por STREAM](#leer-archivo-por-stream)
    - [Crear un SERVIDOR](#crear-un-servidor)
    - [Uso de Request](#uso-de-request)
    - [Uso de Response](#uso-de-response)
    - [Regresar HTML](#regresar-html)

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

```javascript
const fs = require('fs')
if(!fs.existsSync('newfolder')){
	fs.mkdir('newfolder',(err,data)=>{
		if(err){
			console.log('Algo raro ha pasado')
		}else{
			console.log('Directorio creado')
		}
	})
}else{
	console.log('Ese directorio ya existe...')
}
```
### Leer archivo por STREAM

```javascript
const fs = require('fs')

const readStream = fs.createReadStream('largeFile.txt')
readStream.on('data',chunk=>{
  console.log('### Chunk de datos ###')
  console.log(chunk.toString())
})
```

### Crear un SERVIDOR

```javascript
const http = require('http');
const port = 3000;

const server = http.createServer((req, res)=>{
  console.log("A request is made");
});

server.listen(port,()=>{
  console.log(`listening on port ${port}`);
});
```
> Si ejecutamos esto, aparentemente funciona, pero... <br/>
> Si abrimos el navegador con **localhost:3000** NO hace nada!

### Uso de Request

> Al crear el servidor enviamos un **request** y un **response**

```javascript
const http = require('http');
const port = 3000;

const server = http.createServer((req, res)=>{
  console.log(`Solicitamos la url: ${req.url}`);
  console.log(`por medio de: ${req.method}`);
});

server.listen(port,()=>{
  console.log(`listening on port ${port}`);
});
```

- [x] Ejecutar con **nodemon**
- [x] Observar los cambios al solicitar una página
> Por ejemplo: localhost:3000/contacto

### Uso de Response

```javascript
const http = require('http');
const port = 3000;

const server = http.createServer((req, res)=>{
  res.setHeader('Content-Type','text/plain');
  res.write('Bienvenidos a mi humilde sitio web');
  res.end();
});

server.listen(port,()=>{
  console.log(`listening on port ${port}`);
});
```
> Podemos cambiar la linea de cabecera para usar **HTML**:

```javascript
res.setHeader('Content-Type','text/html');
```

### Regresar HTML

```javascript
const http = require('http');
const port = 3000;
const fs = require('fs')

const server = http.createServer((req, res)=>{
  res.setHeader('Content-Type','text/plain');
  fs.readFile('./view/index.html',(err,data)=>{
    if(err){
      console.log(err)
      res.end()
    }else{      
      res.end(data)
    }
  })
});

server.listen(port,()=>{
  console.log(`listening on port ${port}`);
});
```









