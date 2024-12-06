# PWA

> Son aplicaciones web que usa:
> * Notificaciones PUSH
> * Puede trabajar SIN internet
> * Usa caracteristicas NATIVAS
> * Pesa muy poco 
> * Se actualiza constantemente
> * Son ligeras
> * Tienen que trabajar en un protocolo SEGURO (https)

## Service Worker 

> Es el CORAZON de las Aplicaciones WEB Progresivas
> Es el intermediario entre la pagina web y el INTERNET
> Es un archivo de Javascript

## Repaso Javascript

1. Crear index.html
2. Instalar __http-server__

```bash
sudo npm install http-server -g
```

3. Ejecutar desde la carpeta del proyecto en shell:

```shell
http-server -p 8081
```
* La opcion -p es por si el puerto 8080 _(default)_ está ocupado
* Tambien podemos usar el plugin __live server__ de __VSCode__
* Cancelamos con _ctrl+c_


### CALLBACK HELL

> Se utilizan los callbacks para funciones asíncronas
> Ya que con el return nos regresaría UNDEFINED

```javascript
function sumarUno(numero, callback){
  setTimeout(function(){
    callback(numero);
  }),800;
}

sumarUno(5, function(numeroValor){
  console.log(nuevoValor);
});
```
> Si queremos hacer algo con ese valor regresado o agregar más código
> se crea un programa dificil de mantener
 
### PROMESAS

```javascript
function sumarUno(numero){
  var promesa = new Promise(function(resolve,reject){
    setTimeout(function(){
      resolve(numero+1);
    },800);
  });
  return promesa;
}

sumarUno(5).then(nuevoNumero=>{
  console.log(nuevoNumero);
  return sumarUno(nuevoNumero);
})
.then(nuevoNumero=>{
  console.log(nuevoNumero);
});
```

> Si vamos a regresar el mismo numero que pasamos a la funcion
> solo es necesario poner como parámetro la funcion de promesa:

```javascript
function sumarUno(numero){
  var promesa = new Promise(function(resolve, reject){
    console.log(numero);
    if(numero >=7){
      reject("Numero mayor o igual a 7");
    }
    setTimeout(function(){
      resolve(numero+1);
      
    },1200);
  });
  return promesa;
}

sumarUno(5)
  .then(sumarUno)
  .then(sumarUno)
  .then(sumarUno)
  .then(sumarUno)
  .then(sumarUno)
  .catch(error=>{
    console.log("ERROR EN PROMESA "+error);
  })
```
> Los errores se manejan con el reject
> Nos ayudamos del catch para lanzar los errores generados
<br/>


#### Promise.all

> Nos sirve para regresar promesas 
> pero también cualquier otra cosa en el orden en que se mandan

```javascript
function lento(numero){
  return new Promise(function(resolve, reject){    
    setTimeout(function(){
      resolve(numero+numero);
    },1000);
  });
}

function rapido(numero){
  return new Promise(function(resolve, reject){
    
    setTimeout(function(){
      //resolve(numero+numero);
      reject("valio");
    },100);
  });
}

//lento(9).then(console.log);
//rapido(2).then(console.log);


Promise.all([lento(1),rapido(5),true])
  .then(respuestas=>{
    console.log(respuestas);
  })
  .catch(console.log);

```

> Si algo llega a fallar, todo falla

#### promise.race

> Pone a competir a las promesas
> que se pasan como parámetro
> y solo importa la que se resuelva primero







































































