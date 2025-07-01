<h1 style="color:#00b4d8">Javascript desde CERO</h1>

> De este curso solo tomaré anotaciones importantes Javascript

- [x] Guardar datos:

```localStorage.setItem("nombre","Fernando");```


- [x] Recuperar elemento:

```console.log(localStorage.getItem("titulo"));```


- [x] Guardar objeto:

> Debemos convertir el objeto __texto__ para transferirlo

```javascript
var usuario = {
    nombre:"Fernando",
    correo:"lfpereag@gmail.com" 
};

localStorage.setItem("usuario",JSON.stringify(usuario));
```

- [x] Recuperar objeto:

> Debemos convertir el texto de nuevo a __objeto__

```javascript
var userjs = JSON.parse(localStorage.getItem(usuario));
console.log(userjs);
```















