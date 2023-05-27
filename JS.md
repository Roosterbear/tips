# Javascript

## LET
Used instead _var_ to declare variables in the new standard. <br/>
Javascript read all the _var_ variables first. Every __let__ is read when is created. <br/>

## CONST
Used to keep values that won't change, as DOM Elements, Arrays, Objects and __Constant__ values.

## SCOPE
Scope is the context or visibility of variables, functions and objects in our code. <br/>
It determines how and where a particular identifier can be accessed. <br/>
It is very important for avoiding naming conflicts and controlling access to variables and functions. <br/>
We can create a scope with a function or a try-catch to block access to that variables.

## STRINGS

__String interpolation__ <br/>
We can add text with variables in a better way with the ``` ` ``` sign. <br/>

```javascript
const activities = ['walking', 'reading', 'coding'];
const message = `My name is Fernando and I love ${activities
  .map(function(activity){
    return `${activity}!!`
  })
  .join(', ')
}`
console.log(message);

```

__Remove blank spaces in a text__ <br/>
We can use the __.trim()__ function to remove blank spaces in a text variable.

## ARRAYS
We can create an array this way: <br/>
```javascript
const arreglo1 = [1,2,3,4,5,6,7];
```

#### Array Methods

__Filter__<br/>
__Returns__ _a new array_ with the values that return true in a given condition.<br/>
Iterates the array to evaluate every value within a condition. <br/>

```javascript
let hiWords = ["hey", "hi", "hello"];
hiWords = hiWords.filter(x=>x.indexOf("he")===0);
console.log(hiWords);
```

__Map__<br/>
__Returns__ _a new array_ with the modified values of the array. <br/>

```javascript
const arreglo1 = [1,2,3,4,5,6,7];
const arreglo2 = arreglo1.map(n=>n*2);
console.log(arreglo2);
```

## FUNCTIONS

__rest__ <br/>
We can accept unknown number of elements in a function with "rest" <br/>
The only thing we have to do is add "..." and the variable that will receive the data as an array. <br/>
It ONLY can be possible if that value is the __last__ of the parameters. Otherwise, we will get an ERROR!. <br/>

```javascript
function fruits (fruit1, ...rest_of_fruits){
  console.log(fruit1);
  console.log(rest_of_fruits);
}

fruits("apple", "banana", "orange", "fig", "blackberry", "melon", "papaya", "mamme");
```

__spread__ <br/>
We can pass as an argument an array: <br/>

```javascript
function fruits (fruit1, ...rest_of_fruits){
  console.log(fruit1);
  console.log(rest_of_fruits);
}

const other_fruits = ["strawberry", "lemon", "watermelon"];

fruits(...other_fruits, "apple", "banana", "orange", "fig", "blackberry", "melon", "papaya", "mamme");
```

We can separate a word by letters: <br/>

```javascript
const message = 'hello';
const chars = [..message];

console.log(chars); // Will print ['h','e','l','l','o'];
```

And we can separate arguments:

```javascript
function add(a,b,c){
  return a+b+c;
}

const arr = [2,4,6];
console.log(add(...arr)); // 12!
```



    function sum(...numbers) {
        return numbers.reduce((acc, number) => acc + number);
    }
     
    const answer = sum(1, 5, 20, 10);
     
    console.log(answer);








    const names = [
     'bob', 
     ...[
         'donald'
     ],
     'suzy', 
     'lacy',
     ...[
         'richard', 
         'alex'
     ]
    ]
    console.log(names);








    const sum = Math.min(...[1, 5, -1, -10])
    console.log(sum);








    function underscore (strings, ...values) {
        return strings[0].replace(/\s/g, '_');
    }
     
    const message = underscore`there      is no cow level`
     
    console.log(message);
    
    
    
    
    
    
    
        function error (strings, err) {
        error = `status: ${err.status}, message: ${err.message}`
        return `${strings[0]}{${error}}`
    }
     
    const err = {
        message: 'oh no, an error!',
        status: 404
    }
     
    const message = error`An error has occurred: ${err}`
     
    console.log(message);

__arrow function__ <br/>
Is a new way to create a function, and has some advantages: <br/>

1.- More readable code, specially in array methods and event handlers <br/>
2.- No binding of "this". Traditional functions create new "this" when invoked as methods or constructors. <br/>
3.- Lexical "this" value. Inherit it from the encolsing scope. Making it easy to maintain. <br/>
4.- Implicit return. We can do a one line function without the return statement, as long as the funtion body is a single expression. <br/> 
5.- Have a shorter and more concise syntax, creating compact and expressive code. <br/>

```javascript

```

__objects in array functions__

```javascript
const arr = [1,2,3,4,5];

const byTwo = arr.map(number=>(
{
  number: number*2;
}
));

byTwo;
```

__property shorthand__

```javascript
var firstname = 'Fernando';
var lastname = 'Roosterbear';
var age = 20;

// We create an object with the same names as the variables which we used to create it.
var person = {
  firstname,
  lastname,
  age
}
```

__computed property names__

```javascript
var key = lastname;
function mailFn(){
  return 'mail';
}

const work = ()=>'work';

var person = {
  firstname: 'Fernando',
  [key]: 'Roosterbear',
  [mailFn()]: 'fernandoroosterbear@gmail.com',
  ['age']: 20,
  [work()+'_mail']:'fernando@ibm.com'
}


```
<br />
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

Async Javascript deals with the performs of tasks which takes some time to complete. <br/>
Starts now and finish later. <br/>

__Promises with Class Promise, then, resolve and reject__ <br/>
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

__Promises with Async and Await__ <br/>

__Async__ is a way to use promises in any function.
__Await__ can be used only with a function in Async and stops the program to wait an answer.






