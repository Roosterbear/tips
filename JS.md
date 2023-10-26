# JAVASCRRIPT

We can add Javascript code in an HTML file with the __script__ tag. <br/>


```html
<script src="app.js"></script>
```

* Normally we used to write that line above the _body_ __CLOSE__ tag
* We can add that line inside the _head_ tag, but sometimes we get troubles because the JS code requires the DOM to be loaded first.

In that cases where we have to add the line inside the head tag, we can use: <br/>

* A listener with DOMContentLoaded to enclose our JS code.
* Add __defer__ inside the _script_ open tag.

```html
<script src="app.js" defer></script>
```

## LET
Used instead _var_ to declare variables in the new standard. <br/>
Javascript read all the _var_ variables first. Every __let__ is read when is created. <br/>

## CONST
Used to keep values that won't change, as DOM Elements or __Constant__ values. Also objects and arrays. <br/>

## SCOPE
Scope is the context or visibility of variables, functions and objects in our code. <br/>
It determines how and where a particular identifier can be accessed. <br/>
It is very important for avoiding naming conflicts and controlling access to variables and functions. <br/>
We can create a scope with a function or a try-catch to block access to that variables.

## STRINGS

### TRIM

Remove spaces at the start and the end of a text <br/>

```javascript
const text = "      this is a text        ";
let _text = text.trim();
```

Remove just the start of a text <br/>

```javascript
const text = "      this is a text        ";
let _text = text.trimStart();
```

Remove just the end of a text <br/>

```javascript
const text = "      this is a text        ";
let _text = text.trimEnd();
```
<br/>

### SPLIT

Separates a text in characters into an Array. <br/>

```javascript
const text = "UNITED";
let _text = text.split('');
```

Separates a text by words based on a character into an Array <br/>
In this case, we do not use any character, 

```javascript
const text = "this is a text with spaces";
let _text = text.split(' ');
```

### JOIN

Join the members of an Array, and can add a given character between them. <br/>

```javascript
const text = "this is a text with spaces";
let _text = text.split(' ');
let _new = _text.join('*');
```

__remove all spaces with split and join__ <br/>

```javascript
const texto = "    Texto de ejemplo     "
let procesado
procesado = texto.split(" ").join("") // > "Textodeejemplo"
```

### REPLACE

Replace the first occurrence of the first parameter with the content of the second parameter <br/>

```javascript
const text = "HARRY POTTER";
let movie = text.replace('H', 'Mr. H'); // Mr. HARRY POTTER
```

__replace with regEx to get rid blank spaces__ <br/>

```javascript
const texto = "    Texto de ejemplo     "
let procesado
procesado = texto.replace(/\s+/g, '')  // > "Textodeejemplo"
```
__LOOK THAT regEx DOESN'T NEED QUOTES__ <br/>
<br/>

__expressions meanings__ <br/>

__\s__ select blank SPACES, tabs and line breaks <br/>
__+__  along with _\s_, takes more than one consecutive spaces <br/>
__g__  allows tracking the process throughout the string <br/>
<br/>


__replace with regEx to get rid extra characters__ <br/>

```javascript
const texto = "Hola, este es un ejemplo!. No quiero signos como +, -, *. Tampoco guiones?. --"
let procesado
procesado = texto.toLowerCase().replace(/[]/gi, '')  
```

__expressions meanings__ <br/>

__g__  GENERAL. Allows tracking the process throughout the string <br/>
__i__  INDISTINCT. No matter if it is lowercase or uppercase <br/>
<br/>




## STRING INTERPOLATION
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

## CONSOLE

We can print a result or variables in the console to check our programs, and we can do it like:

```javascript
const hello="hello"
const world="world"

// Tired and boring way
console.log("This is a typical "+hello+" "+world)

// Alternative way like others programming languages
console.log("This is a typical %s %s", hello, world)

// Best JS way
console.log(`This is a typical ${hello} ${world}`)

```

__check if is not a number__ <br/>

__isNaN(1)__: false, it is a number actually
__isNaN(null)__: false, converted to 0, which is a number
__isNaN(false)__: false, converted to 0, which is a number
__isNaN("$10")__: true, dollar sign is not a digit
__isNaN(undefined)__: true, converted to NaN
__isNaN()__: true, implicitly undefined, converted to NaN

__infinity__ <br/>

Is equal to _infinity_, in other words, the maximum number. <br/>

```javascript
console.log(Number.MAX_VALUE * 2)
```

__Remove blank spaces in a text__ <br/>
We can use the __.trim()__ function to remove blank spaces in a text variable.

## ARRAYS
We can create an array this way: <br/>

```javascript
const arreglo1 = [1,2,3,4,5,6,7];
```

## FILTER

__Returns__ _a new array_ with the values that return true in a given condition.<br/>
Iterates the array to evaluate every value within a condition. <br/>

```javascript
let hiWords = ["hey", "hi", "hello"];
hiWords = hiWords.filter(x=>x.indexOf("he")===0);
console.log(hiWords);
```

## MAP

__Returns__ _a new array_ with the modified values of the array. <br/>

```javascript
const arreglo1 = [1,2,3,4,5,6,7];
const arreglo2 = arreglo1.map(n=>n*2);
console.log(arreglo2);
```

__Reduce__<br/>

🕦 


__Find__<br/>

🕦 


__Some__<br/>

🕦 


__Every__<br/>

🕦 


__Reverse__<br/>

🕦 


## FUNCTIONS

You know what functions are, don't you?. <br/>
Is a piece of code that we can use over and over again, avoiding repeat typing. <br/>
Remember: __DO NOT REPEAT YOURSELF__ <br/>
The normal functions have the text __function__ and the name of the function and parentheses beside it. <br/>
Then we enclose the content in curly braces, like: <br/>

```javascript
function myFunction(){

// The content of the function

}
```

__first-class citizens function__ <br/>
Is the __fact__ that a function can be passed around like any other value, and be trated equal to other types. <br/>

We can store functions in variables: <br/>
```javascript
const add = (a, b)=>a + b;
```

We can store functions in a property: <br/>
```javascript
const counter = {
  value: 23, 
  inc: function(){
    this.value++;
  }
}
```

We can __pass__ functions as arguments to _other_ functions: <br/>

```javascript
const greet = ()=>console.log('Hello world!');
btn.addEventListener('click', greet);
```
In this case, __greet__ is the first class function. <br/>


__higher-order functions__ <br/>
Is a function that takes another function as a parameter, or returns a new function or both. <br/>
This is possible because first-class citizen functions  in JS. <br/>

```javascript
const greet = ()=>console.log('Hello world!');
btn.addEventListener('click', greet);
```
In this case, addEventListener is the higher order function, that receives a function as parameter. <br/>
That function passed as parameter is known as __callback__ function. <br/>

```javascript
function count(){
  let counter = 0;
  return function(){
    counter++;
  };
}
```

Now, count is a higher order function that returns a new function. <br/>

### Event Listeners

We can add listeners to the DOM and adding it an anonymous function like: <br/>

```javascript
const inputEmail = document.querySelector('#email');
inputEmail.addEventListener('blur', function(e){
  console.log(e.target.value);
});
```

But we can add a function like:

```javascript
const inputEmail = document.querySelector('#email');
inputEmail.addEventListener('blur', validate);

function validate(){
  console.log('From somewhere in the form...');
}
```

🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 <br/>
__Is extremely important to remeber that we have not to add parenthesis__ <br/>
_If we call a function with parenthesis, we invoke it automatically_ <br/>
### To bind a function to a Event Listener, we have to add it without PARENTHESIS !
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 <br/>
<br/>


__document.addEventListener("DOMContentLoaded", () => {});__ <br/>

Waits for HTML code to load, is faster. <br/>
     
__window.addEventListener('load', () => {});__ and __window.onload = () => {};__ <br/>

Waits for whole page to load (HTML, CSS, images, plugins, and so on), is slower. <br/>
     

__objects in array functions__ <br/>

```javascript
const arr = [1,2,3,4,5];

const byTwo = arr.map(number=>(
{
  number: number*2;
}
));

byTwo;
```

__property shorthand__ <br/>

We create an __object__ with the SAME NAMES as the _variables_ which we used to create it.

```javascript
var firstname = 'Fernando';
var lastname = 'Roosterbear';
var age = 20;

var person = {
  firstname,
  lastname,
  age
}
```

__computed property names__ <br/>

We can use _variable_ names, _function_ names, _strings_ and returned values as __properties__ in objects: <br/>

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

__method properties__ <br/>

Is a new way to define methods in objects. <br/>

```javascript
var person = {
  name: 'Fernando',
  age: 20,
  haveBirthday (){
    this.age++;
  }
}

person.haveBirthday();
console.log(person);

```

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

We can separate a text by letters: <br/>

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

__arrow function__ <br/>
Is a new way to create a function, and has some advantages: <br/>

1.- More readable code, specially in array methods and event handlers <br/>
2.- No binding of "this". Traditional functions create new "this" when invoked as methods or constructors. <br/>
3.- Lexical "this" value. Inherit it from the encolsing scope. Making it easy to maintain. <br/>
4.- Implicit return. We can do a one line function without the return statement, as long as the funtion body is a single expression. <br/> 
5.- Have a shorter and more concise syntax, creating compact and expressive code. <br/>

```javascript
const flecha = ()=>{
  return 'hello';
}
```


🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 <br/>
__Is extremely important to remeber that we must NOT use arrow functions as methods!__ <br/>
_Arrow functions DO NOT have THIS_ <br/>
### We can use arrow functions inside a method, BUT not AS methods.
🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 🔥 <br/>
<br/>





__functions accepting callback functions__ <br/>

We are going to create a function that takes a set of words and replaces them with a single string <br/>
converted to lowercase. <br/>

```javascript
const oneWord = function(str){
  return str.replace(/ /g, '').toLowerCase();
}
```
The __g__ stands for _"global"_ that is to say: "all occurrences". <br/>
We receive a string, then is replaced for a single string without blank spaces in lowercase. <br/>


Now, let's do a function that takes the first text and change it to uppercase: <br/>

```javascript
const upperFirstWord = function(str){
  const [first, ...others] = str.split(' ');
  return [first.toUpperCase(), ...others].join(' ');
};
```

Now we can use both functions to pass it like callback in other function: <br/>

```javascript
const transformer = function(str, callback){
  console.log(`Original string: ${str}`);
  console.log(`Transformed string: ${callback(str)}`);
  console.log(`Transformed by: ${callback.name}`);
}

transformer('Javascript is the best!', upperFirstWord);
transformer('Javascript is the best!', oneWord);

```


__functions returning functions__ <br/>

We need __two__ functions, the main function <br/>
and the anonymous function that is returned. <br/>

```javascript
const greet = function(greeting){
  return function (name){
    console.log(`${greeting} ${name}`);
  };
};

const greeterHi = greet('Hi');
const greeterHey = greet('Hey');

greeterHey('Juan');
greeterHi('Fernando');
// greet alone
greet('Hello')('Marylu');
```

How can we do it with __arrow functions__? <br/>

```javascript
const greet = greeting=>name=>{
    console.log(`${greeting} ${name}`);
};
```

__call method__ <br/>

Is a way to have functions that could use objects data. <br/>

```javascript
const bs = {
    name: `Like Dylan in the movies`,
    band: `Belle and Sebastian`
}

const baba = {
    name: `Putita`,
    band: `Babasonicos`
}

const Walkman = {
    name: 'Sony',
    reproducir: function(){
        console.log(`This walkman is playing ${this.name} by ${this.band}`)
    }
}

Walkman.reproducir.call(bs);
Walkman.reproducir.call(baba);
```

__apply method__ <br/>

🕦 


__bind method__ <br/>

🕦 


__closures__ <br/>

🕦 


## CLASSES

```javascript
class Person{
  constructor(name, age){
    this.name = name;
    this.age = age;
  }
  jump(){console.log('The Person Jumps!')}
}

class Employee extends Person{
  constructor(name, age, years){
    super(name, age);
    this.years = years;
  }
  jump(){console.log('The Employee jumps now')}
}
```

__static members__ <br/>

```javascript
class Person{
  constructor(name, age){
    this.name = name;
    this.age = age;
  }
  static setName(person, name){
    person.name = name;
  }
}

const person = new Person('Fer', 46);
Person.setName(person, 'Luis');
console.log(person);

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
__querySelectorAll__ returns all coincidences into an array <br/>

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
## OBJECTS

We have two kind of __objects:__ <br/>

__object literals__ <br/>

```javascript
const Cliente = {
  nombre: this.nombre,
  saldo: this.saldo
}
```

__object constructor__ <br/>

```javascript
// Function constructor 
function Persona(nombre, apellido){
  this.nombre = nombre;
  this.apellido = apellido;
}
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

let designer = new Persona('Coraline','Jones');
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

__Symbols__ <br/>

Is a _primitive_ data type. <br/>

It creates unique properties. <br/>

```javascript
const id = Symbol('id');
const persona = {
  [id]: 12345,
  nombre: 'Juan',
  edad: 30
};

console.log(persona[id]); // 12345
```javascript

Helps to avoid collitions. <br/>

Used in constants: <br/>

```javascript
const EVENT_CLICK = Symbol('click');
element.addEventListener(EVENT_CLICK, () => {
  // Manejar el evento de clic
});
```

__Iterators with Symbols__ <br/>

```javascript
const obj = {
  number: 53820391,
  [Symbol.iterator]() {
    let currentIndex = 0;
    const values = [this.number];

    return {
      next() {
        if (currentIndex < values.length) {
          return { value: values[currentIndex++], done: false };
        } else {
          return { done: true };
        }
      }
    };
  }
};

// Iterar sobre el objeto iterable
for (const item of obj) {
  console.log(item);
}
```

__Iterators__ <br/>

```javascript

function myIteration(cart){
  let i = 0;

  return{
    next: ()=>{
      const fin = (i >= cart.length);
      const valor = !fin? cart[i++]:undefined;

      return{
        fin,
        valor
      }
    }
  }
}


const cart = ['product1', 'product2', 'product3'];

const theIteration = myIteration(cart);

console.log(theIteration.next());
console.log(theIteration.next());
console.log(theIteration.next());
console.log(theIteration.next());
```
<br/>

__more iterators__ <br/>

```javascript
const myArray = [1,2,3];
const mySet = new Set(1,2,3);
const myMap = new Map();

myMap.set('name','Fernando');
myMap.set('lastName','Roosterbear');

/* ENTRY */
for(let entry of myArray.entries()){
  console.log(entry);
}

/* VALUE */
for(let value of myArray.values()){
  console.log(value);
}

/* KEY */
for(let key of myArray.keys()){
  console.log(key);
}

/* DEFAULT */

// Returns value by default
for(let a of myArray){
  console.log(a);
}

// Returns value by default
for(let s of mySet){
  console.log(s);
}

// Returns both: key and value by default
for(let m of myMap){
  console.log(m);
}
```

__Promises with Async and Await__ <br/>

__Async__ is a way to use promises in any function. <br/>
__Await__ can be used only with a function in Async and stops the program to wait an answer. <br/>




### defer

Helps if you __need__ to add script tag in the head. <br/>

```html
<script src="script.js" defer></script>
```

## NEW PROJECT ES6

Create a __new__ folder. <br/>

>mkdir myproject
>cd myproject

Use npm init to create the __package.json__ <br/>

>npm init -y

Install __Webpack__ inside the project: <br/>

>npm i --save-dev webpack
>npm i --save-dev webpack-dev-server



🕦  checking this from a book ---




Install __Babel__ inside the project: <br/>

```terminal
npm install @babel/core @babel/cli --save-dev
npm install @babel/preset-env --save-dev
```

Create the file _.babelrc_ and add: <br/>

```javascript
{
  "presets" : ["@babel/preset-env"]
}
```

Now, to teste __Babel__ we just create a file _before.js_ with modern JS code. <br/>
Go to terminal and type: <br/>

```terminal
node_modules/.bin/babel before.js -o after.js
```





