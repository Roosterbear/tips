<h1 style="color:#c1121f">Tips de Videos en Youtube</h1>

- [App sencilla en Node con Express](#app-sencilla-en-node-con-express)
  - [Agregar una Vista](#agregar-una-vista)
  - [Agregar un ID](#agregar-un-id)
- [Búsquedas Avanzadas en Google](#búsquedas-avanzadas-en-google)
- [Githubs interesantes](#githubs-interesantes)


# App sencilla en Node con Express

- [x] Instalar```npm init```
- [x] Instalar```npm install express```
- [x] Instalar```npm install -g nodemon```

```javascript
const express = require('express');
const app = express();
const server = require('http').Server(app);

app.get('/', (req, res)=>{
    res.status(200).send("Hello World");
});

server.listen(3030);
```
- [x] Ejecutar con ```nodemon server.js```
- [x] Abrir en navegador web: ```localhost:3030```


## Agregar una Vista

- [x] Instalar __EJS__: ```npm install ejs```
- [x] Crear un archivo __views/room.ejs__ con código HTML
- [x] Agregar antes del __app.get__: ```app.set('view engine', 'ejs');```
- [x] Sustituir el texto en __app.get__ por: ```res.render('room');```

## Agregar un ID

- [x] Instalar __UUID__ por: ```npm install uuid```

```javascript
const express = require('express');
const app = express();
const server = require('http').Server(app);
const { v4: uuidv4 } = require('uuid');
app.set('view engine','ejs');
app.use(express.static('public'));

app.get('/', (req, res)=>{
    res.redirect(`/${uuidv4}`);
})

app.get('/:room', (req, res)=>{
    res.status('room', {roomId: req.params.room});
})
```
- [x] Agregamos script desde el room.ejs: ```console.log("<%=roomId %>");```




# Búsquedas Avanzadas en Google

- [x] Quitar opciones de busqueda

```busqueda -periodista -futbolista ```

- [x] Buscar paginas wordpress

```site:*.gob.mx inurl:wp-admin```

- [x] Buscar paginas inseguras

```site:*.gob.mx inurl:http```

- [x] Buscar paginas abiertas

```site:*.mx intitle:"index of/documents"```


# Githubs interesantes

```https://github.com/threat9/routersploit```
```https://github.com/thewhiteh4t/seeker```
```https://github.com/ultrasecurity/Storm-Breaker```







``` ```
``` ```
``` ```
``` ```
``` ```
``` ```
``` ```
``` ```






























