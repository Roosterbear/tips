# WEB

## All about Web Programming

### HTML, CSS and Tools

---

# HTML

---

### Basic structure

We need tags to work with __HTML__<br/>
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="shortcut icon" href="favicon.ico" />
  <title>The Name of the Web Site</title>
</head>
<body>
  <!-- All the content -->
</body>
</html>
```


### Fonts

We can add new fonts this way: <br/>
```html
@font-face {
  font-family: 'MyFont';
  src: url('ruta/a/mifuente.woff2') format('woff2'),
       url('ruta/a/mifuente.woff') format('woff');
}

.elemento {
  font-family: 'MyFont', Arial, sans-serif;
}
```

Google fonts to try...<br/>

__Headers, Tittles__ <br/>
Oswald, Amatic SC, Oregano, Alegreya, Flamenco, Lato, Tangerine, Lobster, GochiHand, <br/>
Roboto, Merriweather, Raleway, Montserrat, Rock Salt, Cinzel, Poiret One, Indie Flower, Ruda, <br/>
Permanent Marker, Kalam, Bangers, Gruppo, Cairo, Teko, Abril Fatface, Gloria Allelujah. <br/>

__Content__ <br/>
Source Sans Pro, Asap, Nunito, Open Sans, Cardo, Merriweather, Abel, Ruda, Teko, Arsenal, Homenaje, <br/>
Signika Negative, Playfair Display.<br/>

### Colors

__AQUA__ _#00FFFF_ <br/>
__BEIGE__ _#F5F5DC_ <br/>
__BROWN__ _#A52A2A_ <br/>
__CHOCOLATE__ _#D2691E_ <br/>
__DARK GREY__ _#A9A9A9_ <br/>
__STEEL BLUE__ _#4682B4_ <br/>
__GOLD__ _#FFD700_ <br/>
__WHEAT__ _#F5DEB3_ <br/>
__INDIGO__ _#4B0082_ <br/>
__IVORY__ _#FFFFF0_ <br/>
__LAVENDER__ _#E6E6FA_ <br/>
__MAROON__ _#800000_ <br/>
__NAVY__ _#000080_ <br/>
__OLIVE__ _#808000_ <br/>
__ORANGE__ _#FFA500_ <br/>
__SALMON__ _#FA8072_ <br/>
__TOMATO__ _#FF6347_ <br/>
__RUST__ _#B75B43_ <br/>
__CHERRY__ _#B03060_ <br/>
__IRISH__ _#369F69_ <br/>
__SEA GREEN__ _#228A89_ <br/>
__COPPER ROSE__ _#8F5555_ <br/>

## Element
The __HTML__ element has 3 elements: <br />
Opening tag - Content - Closing tag
```html
<p>Hello World</p>
```

## Tag
The tags has no text or closing tag:
```html
<br/>
```

## Attributes
They go inside tag to enhance their self content. <br/>
```html
<div class="mi-clase">Hola</div>
```
It is a good practice to use double quotation mark to name the attributes, <br/>
besides of to separate words with dashes.<br/>


## Tables

__Basic tags__ <br/>
```html
<table>
  <tr>
    <td>Data</td>
  </tr>
</table>
```
We need to create a new row with the tag: ```<tr>``` <br/>
but we can add data inside tags like ```<td>``` only<br/>

__Headers__ <br/>
Instead using the tag ```<td>``` we use: ```<th>```<br/>
 
__Creating sections in a table__ <br/>
We can create 3 extra sections and give them another look with styles thanks to tags: <br/>
For headers: <br/>
```html
<thead>
```
For content: <br/>
```html
<tbody>
```
For footers: <br/>
```html
<tfoot>
```

__Join 2 columns:__
```html
<td colspan="2">
```

__Join 2 rows:__
```html
<td rowspan="2">
```

## Forms

The main tag is ```<form>```<br/>
Usually we have to add 4 items:<br/>
__action:__ is the file that will handle our form<br/>
__method:__ could be "_post_" or "_get_"<br/>
__id:__ it is oriented to handle the element with CSS or javascript<br/>
__name:__ it is oriented to the form submission<br/>

__input__ <br/>
It is used to get information from the user, and could be type: <br/>

```html
<input type="text">
<input type="password">
<input type="hidden">
<input type="radio">
<input type="checkbox">
```
<br/>

__select__ <br/>
It is used to give some options to choose: <br/>

```html
<select id="" name="" class="form-control">
  <option value="0">Selecciona una opcion</option>
  <option value="1">Opcion #1</option>
  <option value="2">Opcion #2</option>
</select>
```

__textarea__ <br/>
It is like an input text, but bigger. <br/>
```html
<textarea rows="3"></textarea>
```

__radio button__ <br/>
We have to use the same _name_ attribute to group radio buttons. <br/>
We can distinguish them with the attribute _id_.<br/>
To select a chosen we use the ```checked=checked``` or ```checked=true``` attribute<br/>
Look at the next code:
```html
<input type="radio" name="sameol" id="radio1">Radio #1<br/>
<input type="radio" name="sameol" id="radio2" checked="checked">Radio #2
```

__buttons__ <br/>

```html
<button>
```

We use the button tag when the button does an action inside the form or an especific job.

```html
<input type="button" value="Click me" onclick="miFuncion()">
```

We use input tag when we need an independent button to do an especififc job, and it's not asociated to a form.


```html
<a href="https://www.google.com" target="_blank">Visit Google</a>
<a href="document.pdf" download>Download</a>
```

We use the 'a' tag when we need navigation actions or external links.

---

# CSS

---

There are 3 ways to add CSS code: <br/>

1.- Adding a special extra file, for example: style.css and adding it's reference: <br/>
```html
<link rel="stylesheet" href="style.css">
```
2.- Between the ```<head>``` and ```</head>``` tags, adding the ```<style>``` and ```<style>``` tags <br />
3.- And the less used and less recommended: Inside tags withe the "_style_" property.<br/>
(_still used in wordpress and old sites_). <br/>
```html
<div style="background-color: #bbb;">Hello</div>
```

### Clean properties

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

## HOW CSS ACTS? 🐉 

Let's see from less to the most priority in how a cascade works:

### Position (1/4)

Cascade sheets takes the values of properties, and change them as if they fall. <br/>

```css
li{
  color: red;
  color: blue;
}
```
It will be __blue__ because acts like a cascade, from top to bottom. <br/>
First, color will be red, but we overwrite to blue later.<br/>

### Specificity (2/4)

There is another reason for CSS to take certain value, and it is the _specificity_, <br/>
where is a degree of the selector value. <br/>

__1.- id__ The most valuated property, like ```#principal``` <br/>
__2.- attribute__ Like ```li[draggable]``` <br/>
__3.- class__ Like ```.my-class``` <br/>
__4.- element__ Like ```li``` <br/>

### Type [the way we add CSS] (3/4)

The most important: <br/>
```html
<div style=""> </div>
```
Less important <br/>
```<style> /* code */<style>```  <br />

The less important <br/>
```html
<link rel="stylesheet" href="style.css">
```
### Importance (4/4)

```css
li{
  color: red !important;
  color: blue;
}
```
It will be __red__ <br/>

<br/>

## FONTS 

__measurements__ <br/>

_px_ standard measurement to divide minimum spaces of color. <br/>
_em_ relative measurement for fonts, it is equal to the letter M size from default font <br/>
_rem_ based on the root font of the HTML <br/>

__rem HACK__ ❗❗❗ <br/>
```html
  font-size: 62.5%; /* 1rem NOW is 10px ❗ */
```

__remove underline__ <br/>

```css
a:hover{
  text-decoration: none; // by default is underline
}
```

__remove the dotted line from links__ <br/>

```css
a{
  outline: none;
}
```

__space between letters__ <br/>

```css
p{
  letter-spacing: .1rem; /* We can use negative numbers */  
}
```

__add indent__

```css
p{
  text-indent: 5px;
}
```

__remove black circles from lists__ <br/>

```css
ul{
  list-style-type: none; /* or shorthand: list-style: */
}
```
We can add: disc, circle, upper-roman, lower-latin, square.


## PREFIXES
Nowadays, it is not necessary to use prefixes (_-o, -moz, -webkit_), since browsers are compatible. <br/>

## CENTER

__center an element__ <br/>

Adding padding: <br/>

```css
#features{
  padding: 7% 15%;
}
```

7% will be top and bottom <br/>
15% will be left and right <br/>

This is perfect for a _section_ <br/>

__center a text__ <br/>

Add a class and centering like: <br/>

```css
.feature-box{
  text-align: center;
  padding: 5%;
}
```

__center blocks__ </br>

```css
img{
  display: block; /* This makes work the margin property */
  margin: 0 auto;
}
```

To get images in a perfect size, we can add: <br/>

```css
  display: block;
  max-width: 100%;
```

Especial for blocks. <br/>

## IMAGES

There are two properties that makes better our images with CSS:

```css
img{
  max-width: 100%;
  display: block;
}
```


## BACKGROUNDS

```css
body{
  background-color: #ffffff;
  background-image: url(fruits.jpg);
  background-repeat: no-repeat;
  background-position: center center;
}
```
 We can use in background-repeat: no-repeat, repeat, repeat-x, repeat-y. <br/>
 
 In background-position, the first center is for top and bottom, the second is for left and right. <br/>
 
 __fixed background__ <br/>
 
 ```css
  background-attachment: fixed;
  background-size: cover;
  height: 95vh;
 ```
 
 __cover__ is used to adapt the background to the entire image regardless of the device. <br/>
 

## SELECTORS

__child__ <br/>

We have this CSS: <br/>

```css
div > strong{
  color: red;
}
```

And we have this HTML: <br/>

```html
<strong>This doesn't change color</strong>
<div><strong>This will be RED actually</strong></div>
```

__descendent__

Is a tag inside other tag, no matter the depth <br/>

```css
div strong{
  color: green;
}
```

We can check this in the HTML: <br/>

```html
<div>
  <header>
    <p>
      <strong>
        It will be green...
      </strong>
    </p>
  </header>
</div>
```

__adyacent__

A tag that follows another.

```css
p + p{
  text-indent: 1.5em;
}
```

__attribute selectors__

```css
a[href ^ = "#"]{  /* Begins with...*/
  color: red; 
}

a[href * = "#"]{  /* Contains...*/
  color: red; 
}


a[href $ = "#"]{  /* Ends with...*/
  color: red; 
}
```

__pseudo-elements__

::after <br/>
::before <br/>
::selection <br/>
::first-letter <br/>
::first-line <br/>
<br/>

__pseudo-classes__
::checked <br/>
::disabled <br/>
::enabled <br/>
::hover <br/>
::focus <br/>
::visited <br/>
::nth-child <br/>
::nth-lastchild <br/>
::first-child <br/>
<br/>

## POSITIONING 🧭 

__static__ <br/>

Takes the default values of the element (block, inline-block, inline): <br/>
It doesn't move from it's original position. <br/>
```css
position: static;
```
__relative__<br/>

Moves it's position based in the container with: __top__ and __left__. <br/>
```css
position: relative;
```

__absolute__<br/>

Moves it's position relative to the nearest positioned ancestor with: __top__ and __left__.<br />
We need that the ancestor to be "relative" to work this position. <br/>
```css
position: absolute;
```

__fixed__<br/>

Position relative to the top left corner of the browser window. <br/>
Sticks like gum, does not move with scroll. <br/>

```css
position: fixed;
```

Ejm. <br/>
Make a blue rectangle 500px width, 300px height and 200px top-left from parent. <br/>
Put a red circle 200px width and 150px top and 250px left. <br/>

__vertical centering__ <br/>

We have to put a height and a line-height with the __same value__. <br/>

__Menu with Float__ (old school) <br/>

```css
nav ul li{
  float: left;
  list-style: none; // get rid of the nasty black balls
  margin: 10px;
}

.clearfix{
  clear: both; // We have to include a div with this class after the menu
}
```
## VARIABLES

we can assign variables: <br/>

```css
:root{
  --primary-color: white;
}
```

We can use them: <br/>

```css
p{
  color: var(--primary-color);
}
```

## BOXES
                                                                                                                                                                     
The elements in CSS has layers from center to the extreme. <br/>
The first level is the content in itself. <br/>
We can have a border outside the content. It can have color and width. <br/>
Between content and border there is a blank __space__ called _padding_. <br/>
We have another __space__, between border and the outside of the element, called _margin_, where the rest of the page are. <br/>


## CHANGING ELEMENTS 🦋 

__Radius__ 🔘 <br/>
To make a picture or a shape rounded, we can add the property:
```css
border-radius: 50%;
```
__Transition__ ⏲️ <br/>
We can use it when something changes. It delays the time that takes from state to other.<br/>
```css
.elemento {
  background: blue;
  transition: background .5s;
}

.elemento:hover {
  background: red;
}
```
_It will take half second to change color._
<br/>

__Keyframes__ <br/>
Used to define animations to apply gradual changes to an element. <br/>
With a keyframe we can define the states between an animation and it's transformation. <br/>
<br/>
We use the rule __@keyframes__ and any name for the animation. <br/>

```css
@keyframes myAnimation {
  0% {
    opacity: 0;
    transform: translateX(-100px);
  }
  50% {
    opacity: 0.5;
    transform: translateX(0);
  }
  100% {
    opacity: 1;
    transform: translateX(100px);
  }
}
```

Now we can apply it: <br/>
```css
.elemento {
  animation-name: myAnimation;
  animation-duration: 3s;
  animation-timing-function: ease-in-out;
  animation-delay: 1s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

__Cursor__ ✋🏼 <br/>
If we want to change the aspect of the mouse cursor, we can chang it with: <br/>
pointer, crosshair, e-resize, grab, help, move, progress, text, wait, no-allowed, no-drop <br/>


## RESPONSIVE DESIGN 🦎

### Media Queries

It is a way to adapt the content to screen sizes. <br/>

```css
@media (min-width: 768px){
  /* CSS only for screens below or equal to 600px width */
}

@media (min-width: 1200px){
  /* CSS only for screens below or equal to 600px width */
}
```

🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎 <br/>
### Flexbox
🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎🦎 <br/>
The Best way to layout inline blocks in ONE DIMENSION ALIGMENT. <br/>
In some way, it moves like _mud in pipes_ <br/>

__1.- We need a parent class to contain flexbox:__ <br/>
```css
.container{
  display: flex;
  gap: 1rem; // Space between elements
}
```

__2.- We need to add the direction at that container with flex-direction:__ <br/>
```css
.container{
  display: flex;
  flex-direction: column; // Or by default: row
  gap: 1rem; // Space between elements
}
```
_We won't see anything until we add elements (items)_. <br/>

__Change the basis__ <br/>
The basis is the axis that we select in flex-direction. <br/>
We can change the size of every element with: <br/>
```css
.container > *{
  flex-basis: 100px;
}
```

__Wrap elements__ <br/>
By default, the elements are displayed in nowrap. <br/>
We must add to the parent: <br/>
```css
flex-wrap: wrap;
```

__Change order of elements__ <br/>
We can change the order of an element with: <br/>
```css
.first{
  order: 10; // will be displayed in the second place
}

.second{
  order: 0; // will be displayed in the first place
}
```

__justify-content__ <br/>

* flex-start 
* flex-end 
* center
* space-between 
* space-around
* space-evenly
<br/>

__align-items__ <br/>
❗ ONLY WORKS WITH NO-WRAP ❗ <br/>

* flex-start _Elements stick to the top edge_
* flex-end _Elements stick to the bottom edge_
* center _if elements have different height, they are centered by the middle in the center of the screen_
* baseline  _If elements have different height, they are centered by the middle in the top of the screen_
* stretch _Elements take all free space_

_To see how it works, we have to add to the parent:_

```css
height: 70vh;
```

_If we want to change the align of only one item we can use in that element:_

```css
align-self: flex-end; // or whatever we want...
```

__Sizing__ <br/>

```css
flex-grow: 0;
flex-shrink: 0;
```

__center elements__ <br/>

```css
display: flex;
justify-content: center;
align-items: center;
```






🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞 <br/>
### GRID Layout
🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞🐞 <br/>

The best way to create complex designs with different size blocks in 2 DIMENSION ALIGMENT. <br/>
in some ways, it moves like _tetris_ <br/>

__1.- We need a parent class to contain Grid Layout:__ <br/>
```css
.grid-layout{
  display: grid;  
}
```

__2.- We have to say how many rows and columns I want:__ <br/>
```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```
_This way, every auto or value are a column._<br/>

__3.- Size of an element:__ <br/>
```css
.box1{
  grid-column: 1/3;
}
```
Where 1 is the first line (not the space ❗). <br/>

```css
.box2{
  grid-row: span: 2;
}
```

__4.- Position of the element:__ <br/>

```css
.astronaut{
  background-color: #03989e;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 3;
}
```

Also we can use just grid-area to set the 4 values: <br/>
```css
.cowboy{
  grid-area: 2 / 1 / 3 / 3; 
}
```
Where the order is: <br/>
1.- grid-row-start <br/>
2.- grid-column-start <br/>
3.- grid-row-end and <br/>
4.- grid-column-end <br/>


## SASS ♥️♥️♥️

♥️ We can have __variables__! <br/>

```sass
$color-primary: #f9ed69;
```

♥️ Nested code <br/>

Instead: <br/>

```css
.nav{
  list-style: none;
}

.nav li{
  display: inline-block;
  margin-left: 30px;
}

.nav li:first-child{
  margin: 0;
}

```

We can: <br/>

```css
.nav{
  list-style: none;
    
  li{
    display: inline-block;
    margin-left: 30px;
  }
  
  &:first-child{
    margin: 0;
  }
}
```

♥️ Mixins: <br/>

__create a mixin:__ <br/>

```sass
@mixin clearfix{
  
}

@mixin coolfont($color){

}
```

__use a mixin:__ <br/>

```sass
@include clearfix;
  
```


__compile SASS__ <br/>

```terminal
npm init
npm install node-sass --save-dev
```

🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️ <br/>
IF WE LOST OUR DEPENDENCY FILES, WE CAN USE:

```node
npm install
```
AND THE PACKAGE.json WILL BE USEFUL TO RE-INSTALL DEPENDENCIES. <br/>
### The difference between --save and --save-dev is that 
### save is for dependencies (for our app) and --save-dev is for developer (to code).
🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️🕷️ <br/>

We need to edit our _package.json_ in the script section: <br/>

```json
"scripts":{
  "compile:sass": "node-sass sass/main.scss css/style.css"
},
```

Where __compile:sass__ is the name of our script. <br/>
_node-sass_ is the command to compile SASS files <br/>
_sass/main.scss_ is the path of our origin SASS files. <br/>
_css/style_ is the path of our final file in CSS. <br/>

<br/>
Now we run: <br/>

```node
npm run compile:sass
```

If we need to be watching in every change, we can add the "-w" parameter.

__gulp__ <br/>

>sudo npm install -g gulp-cli

>npm install --save-dev gulp




## 👁️ SNIPPETS in VSC

__1.- Ctrl+Shift+p and write 'user snippet'__ <br/>
__2.- Select file extension wher to apply__ <br/>
__3.- Write your code like:__ <br/>


```json
"Media Query":{
		"prefix":"mq",
		"body":[
			"@media (min-width: $1px){",
			"\t$2",
			"}"
		]
	}
```

__"Media Query"__ is just the name. <br/>
__"prefix"__ is the trigger, choose a meaningful and short one!. <br/>
__"Body"__ is where the code goes. <br/>
__$1__ The place to write code after trigger our snippet. <br/>
__\n__ A line break. <br/>


```json
"Pictures": {
		"prefix": "im",
		"body": [
			"<picture>",
			"\t<source ",
			"\t\tsizes=\"1920w, 1280w, 640w\"",
			"\t\tsrcset=\"$1.avif 1920w",
			"\t\t\t\t\t\t\t$1-1280.avif 1280w",
			"\t\t\t\t\t\t\t$1-640.avif 640w\"",
			"\t\ttype=\"image/avif\"",
			"/>",
			"\t<source ",
			"\t\tsizes=\"1920w, 1280w, 640w\"",
			"\t\tsrcset=\"$1.webp 1920w",
			"\t\t\t\t\t\t\t$1-1280.webp 1280w",
			"\t\t\t\t\t\t\t$1-640.webp 640w\"",
			"\t\ttype=\"image/webp\"",
			"/>",
			"\t<source ",
			"\t\tsizes=\"1920w, 1280w, 640w\"",
			"\t\tsrcset=\"$1.jpg 1920w",
			"\t\t\t\t\t\t\t$1-1280.jpg 1280w",
			"\t\t\t\t\t\t\t$1-640.jpg 640w\"",
			"\t\ttype=\"image/jpeg\"",
			"/>",
			"\t<img loading=\"lazy\" decoding=\"async\" src=\"$1.jpg\" lazyalt=\"imagen\" width=\"500\" height=\"300\" />",
			"</picture>"
		]
	}
```

<br/>

__open VSC in a terminal from current folder__<br/>

```terminal
code .
```

__VSC in a RECOVERY window mode__<br/>

```terminal
code -r .
```

<br/>


## 👁️ UPLOAD A PROJECT TO GITHUB AS A WEB PAGE

__1.- Create a New Repository__ <br/>
__2.- Add File - Upload Files__ <br/>
__3.- Tab "Settings" - Pages - Branch "main"__ <br/>
__4.- Takes some minutes to be published and we'll have to wait__ 🕜  <br/>

## 👁️ SSH
ssh {__user__}__@__{__host__} <br/>






