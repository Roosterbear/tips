# HTML

## Basic structure

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

## Fonts

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

## COLORS

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


### Element
The __HTML__ element has 3 elements: <br />
Opening tag - Content - Closing tag <br/>

```html
<p>Hello World</p>
```

### Tag
The tags has no text or closing tag:<br/>

```html
<br/>
```

### Attributes
They go inside tag to enhance their self content. <br/>

```html
<div class="mi-clase">Hola</div>
```
It is a good practice to use double quotation mark to name the attributes, <br/>
besides of to separate words with dashes.<br/>


## TABLES

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

## FORMS

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

We use the button tag when the button does an action inside the form or an especific job.<br/>

```html
<input type="button" value="Click me" onclick="miFuncion()">
```

We use input tag when we need an independent button to do an especififc job, and it's not asociated to a form.


```html
<a href="https://www.google.com" target="_blank">Visit Google</a>
<a href="document.pdf" download>Download</a>
```

We use the 'a' tag when we need navigation actions or external links.


