<div style="color:#2a9d8f">

# NODE
</div>

## Proyecto base

1. ```npm init```
2. ```npm install express```
3. ```npm install nodemon```
4. Crear archivo server.js

```javascript
const express = require('express');
const app = express();
const server = require('http').Server(app);

app.get('/',(req, res)=>{
    res.status(200).send("Hello World");
})

server.listen(3030);
```
