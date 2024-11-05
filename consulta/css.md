# CSS =================================================================
 
## INTRODUCTION

### Add CSS file ------------------------------------------------------

```html
<link rel="stylesheet" href="style.css">
```

### Clean properties ---------------------------------------------------

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

## HOW CSS ACTS? 🐉  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> Let's see from less to the most priority in how a cascade works:

### Position (1/4) ----------------------------------------------------

> Cascade sheets takes the values of properties, 
> and change them as if they fall. 

```css
li{
  color: red;
  color: blue;
}
```
> It will be __blue__ because acts like a cascade, 
> from top to bottom.
> First, color will be red, but we overwrite to blue later.

### Specificity (2/4) -------------------------------------------------

> There is another reason for CSS to take certain value, 
> and it is the _specificity_, <
> where is a degree of the selector value.

1. __id__ The most valuated property, like ```#principal``` 
2. __attribute__ Like ```li[draggable]``` 
3. __class__ Like ```.my-class``` 
4. __element__ Like ```li``` 


### Type [the way we add CSS] (3/4) -----------------------------------

> The most important:

```html
<div style=""> </div>
```
> Less important 

```<style> /* code */<style>```  

> The least important

```html
<link rel="stylesheet" href="style.css">
```
### Importance (4/4) --------------------------------------------------

```css
li{
  color: red !important;
  color: blue;
}
```
> It will be __red__ 



## FONTS --------------------------------------------------------------

### Measurements

> _px_ standard measurement to divide minimum spaces of color. 
> _em_ relative measurement for fonts, 
> it is equal to the letter M size from default font 
> _rem_ based on the root font of the HTML


### rem HACK❗❗❗

```html
  font-size: 62.5%; 
```
> 1rem NOW is 10px ❗


### Remove underline

```css
a:hover{
  text-decoration: none; // by default is underline
}
```

### Remove the dotted line from links

```css
a{
  outline: none;
}
```

### Space between letters

```css
p{
  letter-spacing: .1rem; /* We can use negative numbers */  
}
```

### Add indent

```css
p{
  text-indent: 5px;
}
```

### Remove black circles from lists

```css
ul{
  list-style-type: none; /* or shorthand: list-style: */
}
```
> We can add: disc, circle, upper-roman, lower-latin, square.


## CENTER -------------------------------------------------------------


### Center an element

> Adding padding:

```css
#features{
  padding: 7% 15%;
}
```
> 7% will be top and bottom 
> 15% will be left and right

> This is perfect for a _section_ 

### Center a text

> Add a class and centering like:

```css
.feature-box{
  text-align: center;
  padding: 5%;
}
```

### Center blocks

```css
img{
  display: block; /* This makes work the margin property */
  margin: 0 auto;
}
```

> To get images in a perfect size, we can add: 

```css
  display: block;
  max-width: 100%;
```
> Especial for blocks


### Vertical centering

> We have to put a height and a line-height with the __same value__. 

```css
.box{
  text-align: center;
  height: 100px;
  line-height: 100px;
}
```


## IMAGES -------------------------------------------------------------

> There are two properties that makes better our images with CSS:

```css
img{
  max-width: 100%;
  display: block;
}
```


## BACKGROUNDS --------------------------------------------------------

```css
body{
  background-color: #ffffff;
  background-image: url(fruits.jpg);
  background-repeat: no-repeat;
  background-position: center center;
}
```
 > We can use in background-repeat: no-repeat, repeat, repeat-x, repeat-y. 
 
 > In background-position, the first center is for top and bottom, 
 > the second is for left and right. 
 
 ### Fixed background
 
 ```css
  background-attachment: fixed;
  background-size: cover;
  height: 95vh;
 ```
 
 > __cover__ is used to adapt the background to the entire image 
 > regardless of the device. 
 

## SELECTORS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

### Child

> We have this CSS:

```css
div > strong{
  color: red;
}
```

> And we have this HTML:

```html
<strong>This doesn't change color</strong>
<div><strong>This will be RED actually</strong></div>
```

### Descendent

> Is a tag inside other tag, no matter the depth

```css
div strong{
  color: green;
}
```

> We can check this in the HTML: 

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

### Adyacent

> A tag that follows another.

```css
p + p{
  text-indent: 1.5em;
}
```

### Attribute selectors

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

### Pseudo-elements

::after <br/>
::before <br/>
::selection <br/>
::first-letter <br/>
::first-line <br/>
<br/>

### Pseudo-classes

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

## POSITIONING 🧭  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

### Static

> Takes the default values of the element (block, inline-block, inline): 
> It doesn't move from it's original position.

```css
position: static;
```

### Relative

> Moves it's position based in the container with: __top__ and __left__. 

```css
position: relative;
```

### Absolute

> Moves it's position relative to the nearest positioned ancestor with: 
> __top__ and __left__.
> We need the ancestor to be "relative" to work this position.

```css
position: absolute;
```

### Fixed

> Position relative to the top left corner of the browser window. 
> Sticks like gum, does not move with scroll.

```css
position: fixed;
```

> Ejm.
> Make a blue rectangle 500px width, 
> 300px height and 200px top-left from parent. 
> Put a red circle 200px width and 150px top and 250px left. 

__Menu with Float__ (old school) 

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


## VARIABLES ----------------------------------------------------------

> We can assign variables: 

```css
:root{
  --primary-color: white;
}
```

> We can use them:

```css
p{
  color: var(--primary-color);
}
```

## BOXES --------------------------------------------------------------

> The elements in CSS has layers from center to the extreme. 
> The first level is the content in itself. 
> We can have a border outside the content. 
> It can have color and width. 
> Between content and border there is a blank __space__ called _padding_. 
> We have another __space__, between border and the outside of the element, 
> called _margin_, where the rest of the page are. 


## CHANGING ELEMENTS 🦋  -----------------------------------------------

### Radius 🔘 

> To make a picture or a shape rounded, we can add the property:

```css
border-radius: 50%;
```

### Transition ⏲️ 

> We can use it when something changes. 
> It delays the time that takes from state to other.

```css
.elemento {
  background: blue;
  transition: background .5s;
}

.elemento:hover {
  background: red;
}
```
> It will take half second to change color.



## KEYFRAMES ----------------------------------------------------------

> Used to define animations to apply gradual changes to an element. 
> With a keyframe we can define the states between an animation 
> and it's transformation. 

> We use the rule __@keyframes__ and any name for the animation. 

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

> Now we can apply it: 

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

### Cursor ✋🏼 

> If we want to change the aspect of the mouse cursor, 
> we can chang it with: 
> pointer, crosshair, e-resize, grab, help, move, 
> progress, text, wait, no-allowed, no-drop 


## RESPONSIVE DESIGN 🦎 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

### Media Queries -----------------------------------------------------

> It is a way to adapt the content to screen sizes.

```css
@media (min-width: 768px){
  /* CSS only for screens below or equal to 600px width */
}

@media (min-width: 1200px){
  /* CSS only for screens below or equal to 600px width */
}
```


## Flexbox @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

1. We need a parent class to contain flexbox:

```css
.container{
  display: flex;
  gap: 1rem; 
}
```
> Gap is the space between elements

> __We need at least a child element__


2. We need to add the direction at that container with flex-direction:

```css
.container{
  display: flex;
  flex-direction: column; // Or by default: row
  gap: 1rem; // Space between elements
}
```
> _We won't see anything until we add elements (items)_

### Change the basis

> The basis is the axis that we select in flex-direction. 
> We can change the size of every element with:

```css
.container > *{
  flex-basis: 100px;
}
```

### Wrap elements

>By default, the elements are displayed in nowrap.
> We must add to the parent:

```css
flex-wrap: wrap;
```

### Change order of elements

> We can change the order of an element with:

```css
.first{
  order: 10; 
  /* Will be displayed in the second place */
}

.second{
  order: 0; 
  /* Will be displayed in the first place */
}
```

### justify-content ---------------------------------------------------

* flex-start 
* flex-end 
* center
* space-between 
* space-around
* space-evenly
<br/>

### align-items -------------------------------------------------------

❗ ONLY WORKS WITH NO-WRAP ❗ 

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

### Sizing -------------------------------------------------------------

```css
flex-grow: 0;
flex-shrink: 0;
```

### Center Elements ----------------------------------------------------

```css
display: flex;
justify-content: center;
align-items: center;
```

## GRID Layout @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> The best way to create complex designs with different size 
> blocks in 2 DIMENSION ALIGMENT.
> in some ways, it moves like _tetris_ 

1. We need a parent class to contain Grid Layout:

```css
.grid-layout{
  display: grid;  
}
```

2. We have to say how many rows and columns I want:

```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```
> _This way, every auto or value are a column._

3. Size of an element:

```css
.box1{
  grid-column: 1/3;
}
```

> Where 1 is the first line (not the space ❗).

```css
.box2{
  grid-row: span: 2;
}
```

4. Position of the element:

```css
.astronaut{
  background-color: #03989e;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 3;
}
```

> Also we can use just grid-area to set the 4 values: 

```css
.cowboy{
  grid-area: 2 / 1 / 3 / 3; 
}
```
> Where the order is: 
1. grid-row-start 
2. grid-column-start 
3. grid-row-end and 
4. grid-column-end 


## CSS Art !

### FONDO

* Patrón a seguir para fondo:

1. Altura / Ancho
2. Fondo
3. Posición
4. Transform
5. Bordes
6. Extras

* Crear HTML con etiqueta __DIV__ "container"
* Llamar archivo CSS

```css
.container{
  height: 500px;
  width: 500px;
  background: #4c2e82;
  position: absolute;
  top: 50%;
  left:50%;
  transform: translate(-50%,-50%);
  border-radius: 5%;
  box-shadow: 12px 12px 10px #bbb;
}
```

### Cara

* Agregar DIV "ferb" dentro de "container"

```css
.ferb{
  /* medidas */
  height: 250px;
  width: 60px;
  /* color */
  background: #fce2c4;
  border: 4px solid #ffa945;
  border-bottom: none;
  /* relativo al padre (fondo container)*/
  position: relative;
  /* mover */
  left:220px;
  top: 100px;
  transform: rotate(5deg);
}
```

### Boca

```css
.ferb::before{
  content:"";
  height: 15px;
  width: 15px;
  /* color */
  background: #fce2c4;
  border-left: 5px solid #ffa945;
  border-bottom: 3px solid #ffa945;
  border-bottom-left-radius: 10px;
  /* para moverlo fuera del rostro */
  position: absolute;
  /* mover */
  top: 170px;
  left: -12px;
  transform: skew(-42deg);
}
```

### Oido

```css
.ferb::after{
  content: "";
  height: 25px;
  width: 25px;
  position: absolute;
  /* color */
  background: #fce2c4;
  border-radius: 50%;
  border: 4px solid #ffa945;
  border-top: none;
  border-left: none;
  /* mover */
  left: 55px;
  top: 80px;
  transform: rotate(-40deg);
}
```


### Nariz

* Agregar DIV "nose" bajo "ferb"
```css
.nose{
  height: 50px;
  width: 50px;
  background: #fce2c4;
  position: relative;
  left: 172px;
  bottom: 92px;
  border: 4px solid #ffa945;
  border-right: none;
  border-radius: 12px 0 0 12px;
  transform: rotate(5deg);
  z-index: 100;
}

.nose::before{
  content: "";
  height: 10px;
  width: 30px;
  background: #fce2c4;
  position: absolute;
  left: 30px;
  top: -4px;
  border-top: 4px solid #ffa945;
}

```


### Ojos

* Agregar DIV "eye" bajo "nose"
```css

.eye{
  height: 45px;
  width: 40px;
  background: #fff;
  position: relative;
  left: 206px;
  bottom: 188px;
  border-radius: 50%;
  border: 3px solid #000;
  transform: rotate(5deg);
}

.eye::before{
  content: "";
  height: 12px;
  width: 10px;
  background: #000;
  position: absolute;
  left: 14px;
  top: 22px;
  border-radius: 50%;
  transform: rotate(15deg);
}

.eye::after{
  content: "";
  height: 4px;
  width: 4px;
  background: #fff;
  position: absolute;
  left: 18px;
  top: 24px;
  border-radius: 50%;
}

.second-eye{
  width: 40px;
  height: 40px;
  bottom: 224px;
  left:234px;
}

.second-eye::before{
  top: 10px;
}

.second-eye::after{
  top: 14px;
}
```

### Cabello

* Agregar DIV "hair" bajo "eye" y dentro 5 DIVs sin clase
```css

.hair{
 position: relative;
 left: 10px;
 bottom: 250px;
 z-index: 100; 
}

.hair>div:nth-child(1){
  height: 30px;
  width: 100px;
  position: absolute;
  left: 180px;
  bottom: 40px;
  border-top: 20px solid #008000;
  border-radius: 50px 40px 0 0;
  transform: rotate(30deg);
}

.hair>div:nth-child(2){
  height: 30px;
  width: 100px;
  position: absolute;
  left: 200px;
  bottom: 40px;
  border-top: 20px solid #008000;
  border-radius: 50px 40px 0 0;
  transform: rotate(70deg);
}

.hair>div:nth-child(3){
  height: 30px;
  width: 80px;
  position: absolute;
  left: 220px;
  bottom: 50px;
  border-top: 20px solid #008000;
  border-radius: 50px 40px 0 0;
  transform: rotate(130deg);
}

.hair>div:nth-child(4){
  height: 30px;
  width: 100px;
  position: absolute;
  left: 200px;
  bottom: 20px;
  border-top: 20px solid #008000;
  border-radius: 50px 40px 0 0;
  transform: rotate(20deg);
}


.hair>div:nth-child(5){
  height: 30px;
  width: 50px;
  position: absolute;
  left: 260px;
  bottom: 20px;
  border-top: 20px solid #008000;
  border-radius: 50px 40px 0 0;
  transform: rotate(10deg);
}

```


















