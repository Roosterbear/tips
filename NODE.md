<div style="color:#2a9d8f">NODE</div>

- [App sencilla](#app-sencilla)
  - [Agregar una Vista](#agregar-una-vista)
  - [Agregar un ID](#agregar-un-id)
  - [Agregar Video de la cámara](#agregar-video-de-la-cámara)

# App sencilla

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
- [x] Crear archivo __script.js__ y poner código: ```console.log("<%=roomId %>");```
- [x] Agregamos script desde el __room.ejs__


## Agregar Video de la cámara

```javascript
const myvideoGrid = document.getElementById('video-grid');
const myvideo = document.createElement('video');
myVideo.muted = true;

navigator.mediaDevices.getUserMedia({
    video: true,
    audio: true
}).then(stream=>{
    myVideoStream = stream;
    addVideoStream(myVideo, stream);
})

const addVideoStream = (video, stream)=>{
    video.srcObject = stream;
    video.addEventListener('loadedmetadata', ()=>{
        video.play();
    })
    videoGrid.append(video);
}
```
- [x] Agregamos a __room.ejs__: 

```html
<div id="video-grid">

</div>
```



```
```






































