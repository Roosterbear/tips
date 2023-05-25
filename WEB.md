# ALL ABOUT WEB PROGRAMMING
## HTML, CSS, Basic JS, and Tools

# HTML

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
  <!-- All the content () -->
</body>
</html>
```
### Forms

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


### Fonts
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

## Radio buttons
We have to use the same _name_ attribute to group radio buttons. <br/>
We can distinguish them with the attribute _id_.<br/>
To select a chosen we use the ```checked=checked``` or ```checked=true``` attribute<br/>
Look at the next code:
```html
<input type="radio" name="sameol" id="radio1">Radio #1<br/>
<input type="radio" name="sameol" id="radio2" checked="checked">Radio #2
```

---
# CSS

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

## HOW CSS ACTS?

Let's see from less to the most priority in how a cascade works:

### Position
```css
li{
  color: red;
  color: blue;
}
```
It will be __blue__ <br/>

### Specificity
Cascade sheets takes the values of properties, and change them as if they fall. <br/>
There is another reason for CSS to take certain value, and it is the _specificity_, <br/>
where is a degree of the selector value. <br/>

__1.- id__ The most valuated property, like ```#principal``` <br/>
__2.- attribute__ Like ```li[draggable]``` <br/>
__3.- class__ Like ```.my-class``` <br/>
__4.- element__ Like ```li``` <br/>

### Type (the way we add CSS)
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
### Importance

```css
li{
  color: red !important;
  color: blue;
}
```
It will be __red__ <br/>

<br/>

## Positioning

__static__ <br/>
Takes the default values of the element (block, inline-block, inline): <br/>
It doesn't move from it's original position. <br/>
```css
position: static;
```
__relative__<br/>
Moves it's position with: __top__ and __left__. <br/>
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
```css
position: fixed;
```

Ejm. <br/>
Make a blue rectangle 500px width, 300px height and 200px top-left from parent. <br/>
Put a red circle 200px width and 150px top and 250px left.

## RADIUS
To make a picture or a shape rounded, we can add the property:
```css
border-radius: 50%;
```

<br/>
__Cursor__ <br/>
pointer, crosshair, e-resize, grab, help, move, progress, text, wait, no-allowed, no-drop <br/>


## RESPONSIVE DESIGN

### Media Queries

It is a way to adapt the content to screen sizes. <br/>

```css
@media (max-width: 600px){
  /* CSS only for screens below or equal to 600px width */
}
```
### Flexbox

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

* flex-start
* flex-end
* center
* baseline 
* stretch

_To see how it works, we have to add to the parent:_

```css
height: 70vh;
```

_If we want to change the align of only one item we can use in that element:_

```css
align-self: flex-end; // or whatever we want...
```

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>






# 👁️ UPLOAD A PROJECT TO GITHUB

__1.- Create a New Repository__ <br/>
__2.- Add File - Upload Files__ <br/>
__3.- Tab "Settings" - Pages - Branch "main"__ <br/>
__4.- Takes some minutes to be published and we have to wait__ 🕜  <br/>

# 👁️ SSH
ssh {__user__}__@__{__host__} <br/>






