# Javascript

### Get an element from the DOM 💥 

#### By ID
```javascript
document.getElementById('principal');
```
#### By Tag
```javascript
document.getElementByTagName('ul');
```
#### By Class
```javascript
document.getElementByClass('clase');
```
#### By Element
```javascript
document.querySelector('li a');
document.querySelector('#principal');
document.querySelector('.clase');
document.querySelector('div').innerHTML = 'Hola';
document.querySelector('.btn').style.color = 'red';

```
__querySelectorAll__ returns all coincidences into an array

### Button to add elements at the end of a list
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.append(li);
});
```
### Button to add elements at the end of a list
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.prepend(li);
});
```
### Delete elements of a list added lately
```javascript
ul.addEventListener('click', e=>{
  if(e.target.tagName === 'LI'){
    e.target.remove();
  }
});
```

### Button to delete an element from the list
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.remove();
  });
});
```
### Button to strikethrough an element from the list
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.style.textDecoration = 'line-through';
  });
});
```
---
## CREATE A POP-UP
#### HTML
```html
<button>click me!</button>
<div class="popup-wrapper">
  <div class="popup">
    <div class="popup-close">x</div>
    <div class="popup-content">
      <h2>HOT SALE!</h2>
      <p>50% off Hot panties and tights !</p>
      <a href="#">View</a>
    </div>
  </div>
</div>
```
#### CSS
```css
button{
  display: block;
  margin: 20px auto;
  background: crimson;
  color: white;
  border: 0;
  padding: 6px 10px;  
  // Ocultar popup al inicio
  display: none;
}

.popup-wrapper{
  background: rgba(0,0,0,0.5);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.popup{
  font-family: arial;
  text-align: center;
  width:100%;
  max-width: 300px;
  margin: 10% auto;
  padding: 20px;
  background: white;
  position: relative;
}

.popup a{
  background: crimson;
  color: white;
  text-decoration: none;
  padding: 6px 10px;
}

.popup-close{
  position: absolute;
  top: 5px;
  right: 8px;
  cursor: pointer;
}
```
#### Javascript
```javascript
const  button = document.querySelector('button');
const  popup = document.querySelector('popup-wrapper');
const  close = document.querySelector('popup-wclose');

button.addEventListener('click', ()=>{
  popup.style.display = 'block';
});

close.addEventListener('click', ()=>{
  popup.style.display = 'none';
});

popup.addEventListener('click', ()=>{
  popup.style.display = 'none';
});
```

### A Simple form
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="icon" href="#">
  <title>Javascript Code</title>
  <style>
    body{
      background-color: #eee;
    }
    form{
      max-width: 200px;
      margin: 40px auto;
      background: white;
      padding: 10px;
    }
    input{
      display: block;
      margin: 10px auto;
      padding: 4px;
    }
  </style>
</head>
<body>

  <form class="signup-form">
    <input type="text" id="username" placeholder="username">
    <input type="submit" value="submit">
  </form>
  <script src="script.js" type="text/javascript"></script>
</body>
</html>
```

```javascript
const form = document.querySelector('.signup-form');
const username = document.querySelector('#username')
form.addEventListener('submit', e=>{
  e.preventDefault();
  // We can use the form + the Input ID (works with name either)
  console.log(form.username.value);
  // Also we can use the input ID in a constant directly
  alert(username.value);
});
```

## PROTOTYPES
We need prototypes to ADD features in objects <br/>

```javascript

// Function constructor 
function Persona(nombre, apellido){
  this.nombre = nombre;
  this.apellido = apellido;
}

Persona.prototype.email = 'name@mail.com';

let programmer = new Persona('Ana', 'Karenina');
console.log(programmer.email);

let designer = new Persona('Coroline','Jones');
console.log(designer.email);
```

## CALLBACKS
We use callbacks to include a function as a parameter <br/>

```javascript

function sumar(n1, n2, callback){
  let res = n1+n2;
  callback(res);
}

function imprimirConsole(info){
  console.log("El resultado es: "+info);
}

function imprimirChido(info){
  console.log("+++El resultado es: "+info+"+++");
  console.warn("ESTE FUE UN MENSAJE MUY CHIDO");
}
sumar(5,4,imprimirConsole);
sumar(5,4,imprimirChido);
```

## PROMISES

```javascript
const saludar  = new Promise((resolve, reject)=>{
  
  // We put this timeout to be asynchronous
  setTimeout(()=>{
    let saludo = "Hola mundo";
  
    // we set both cases: if there is a result and if there is no result.
    if (saludo){
      resolve(saludo);
    }else{
      reject('No hay saludo disponible');
    }
  },3000);
});

// Now we have to say what we want to do with the results
// "then" takes the resolve data...
saludar.then(resultado =>{
  console.log(resultado);
})
// DO NOT write a ";" after parenthesis
// "catch" takes the reject data...
.catch(err=>{
  console.log(err);
});
```








