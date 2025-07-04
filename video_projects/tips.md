<h1 style="color:#c1121f">Tips de Videos en Youtube</h1>

- [SaaS App](#saas-app)
- [App sencilla en Node con Express](#app-sencilla-en-node-con-express)
- [App sencilla en Node con Express y una Vista](#app-sencilla-en-node-con-express-y-una-vista)
- [Agregar un ID](#agregar-un-id)
- [Búsquedas Avanzadas en Google](#búsquedas-avanzadas-en-google)
- [Githubs interesantes](#githubs-interesantes)

# SaaS App

- [x] Instalar __NextJS__ ```npx create-next-app@latest```
- [x] __Clerk__
- [x] __shadcn/ui__


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


# App sencilla en Node con Express y una Vista

- [x] Instalar __EJS__: ```npm install ejs```
- [x] Crear un archivo __views/room.ejs__ con código HTML
- [x] Agregar antes del __app.get__: ```app.set('view engine', 'ejs');```
- [x] Sustituir el texto en __app.get__ por: ```res.render('room');```

# Agregar un ID

- [x] Instalar __UUID__ por: ```npm install uuid```
- [x] Agregar a nuestra App __UUID__: ```const { v4: uuidv4 } = require('uuid');```





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






























