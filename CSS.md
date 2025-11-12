<h1 style="color:#AE445A">CSS</h1>

- [FORMATEO](#formateo)
- [CUSTOM PROPERTIES](#custom-properties)
- [CAMBIO DE ELEMENTOS 🦋 ](#cambio-de-elementos-)
  - [Pseudoelementos](#pseudoelementos)
  - [Radius 🔘 ](#radius-)
  - [Transition ⏲️ ](#transition-️)
  - [KEYFRAMES 🔑​](#keyframes-)
  - [BOX SHADOW](#box-shadow)
  - [FILTER](#filter)
    - [ISOLATION](#isolation)
  - [Clip Path](#clip-path)
    - [Sin recortar, pero redondeando las esquinas:](#sin-recortar-pero-redondeando-las-esquinas)
    - [Recortes básicos (top, right, bottom, left):](#recortes-básicos-top-right-bottom-left)
    - [Recortes Circular](#recortes-circular)
    - [Recorte Poligonal](#recorte-poligonal)
    - [Efectos con Clip Path](#efectos-con-clip-path)
  - [Formas de crear un RECTANGULO](#formas-de-crear-un-rectangulo)
  - [Formas de crear un CIRCULO](#formas-de-crear-un-circulo)
  - [Formas de crear un TRIANGULO](#formas-de-crear-un-triangulo)
  - [Formas de crear un HEXAGONO](#formas-de-crear-un-hexagono)
  - [MASK](#mask)
  - [Cursor ✋🏼 ](#cursor-)
- [GRADIENTS](#gradients)
  - [Linear Gradient](#linear-gradient)
  - [Radial Gradient](#radial-gradient)
  - [Conic Gradient](#conic-gradient)
- [RESPONSIVE DESIGN 🦎](#responsive-design-)
  - [Media Queries](#media-queries)
- [Flexbox 🦎](#flexbox-)
  - [Cambiar la base](#cambiar-la-base)
  - [Envolver elementos](#envolver-elementos)
  - [Orden de elementos](#orden-de-elementos)
  - [Justificar elementos](#justificar-elementos)
  - [Alinear Contenido](#alinear-contenido)
  - [Place Content](#place-content)
  - [Alinear Items](#alinear-items)
  - [Align Self](#align-self)
  - [Tamaño de elementos](#tamaño-de-elementos)
  - [Centrar elementos](#centrar-elementos)
- [GRID 🦎](#grid-)
- [CSS Hacks](#css-hacks)

# FORMATEO

- [x] Limpiar Propiedades

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```
- [x] Quitar circulos negros de las __LISTAS__

```css
ul{
  list-style: none; 
}
```

- [x] Eliminar underline de un __ENLACE__

```css
a:hover{
  text-decoration: none; 
}
```
- [x] Altura de linea

```css
font-size: 20px;
line-height: 30px;
```

- [x] Mejor despliegue de una __IMAGEN__:

```css
img{
  max-width: 100%;
  display: block;
}
```

- [x] Cover
  
> Se usa para adaptar el fondo a toda la imagen sin importar el DISPOSITIVO.
 

- [x] __Inherit__

```css
#toolbar{background:blue;color:white;}
```

```html
<div id="toolbar">
  <a href="one.html">One</a> |
  <a href="two.html">Two</a> |
  <a href="three.html">Three</a>
</div> 
```
> Aquí los links heredarán las preferencias del __NAVEGADOR__.
> (probablemente un __azul__ que se ocultará con el fondo azul del __div__)

<br/>

Aquí es cuando entra en acción: <br/>

```css
#toolbar a{color:inherit;}
```
> ACOSTUMBREMONOS A HACER LAS COSAS BIEN

<br/>

> Pudimos poner directamente __white__ en lugar de inherit, pero
> cuando tengamos que cambiar de color, lo haríamos en __DOS__ lugares

* De igual manera, __los bordes NO se heredan__
* por lo que si queremos un borde igual al del padre: <br/>

```css
.hijo {border:inherit;}
```

- [x] Centrar Bloques

```css
img{
  display: block; 
  margin: 0 auto;
}
```

> Podemos agregar: 

```css
  max-width: 100%;
```

- [x] Centrado Vertical

> Ponemos **height** y **line-height** con el mismo valor 

```css
.box{
  text-align: center;
  height: 100px;
  line-height: 100px;
}
```


# CUSTOM PROPERTIES

> No son otra cosa que el uso de __VARIABLES__

```css
html {
  --base-color: #639;--highlight-color: #AEA;
}

h1 {color: var(--base-color);}
h2 {color: var(--highlight-color);}
```


# CAMBIO DE ELEMENTOS 🦋 

## Pseudoelementos

- [X] Son como un __span__ oculto en el CONTENIDO de un elemento
- [X] Existe uno antes __::before__ y otro después __::after__
- [X] Sirven para __agregar__ diseño sin usar otras etiquetas

* Agregar un arreglo a un texto en la parte de arriba 

```css
.texto::before{
  content:''; /* ESTA LINEA ES FORZOSA !! */
  background-color: crimson;
  display:block; /* PARA QUE DEJE DE SER UN SPAN */
  height: 15px;
  width: 25%; /* Solo 1/4 del ancho del texto */
  border-radius: 10px;
  margin-bottom: 1.5rem;
}
```

* Agregar un arreglo a un texto en la parte lateral

```css
.container{display:flex}

.texto::before{
  content:''; /* ESTA LINEA ES FORZOSA !! */
  background-color: crimson;
  display:block; /* PARA QUE DEJE DE SER UN SPAN */
  height: 100%;
  width: 15px; /* Solo 1/4 del ancho del texto */
  border-radius: 10px;
  margin-right: .5rem;
}
```
```nth-child()```

## Radius 🔘 

> Para redondear una foto o elemento podemos agregar:

```css
img{
  border-radius: 50%;
}
```

> Podemos de hecho redondear los bordes de cualquier __caja__:

```css
.box{
  border-radius: 20px;
}
```

> Podemos crear elipses con medidas 

```
```


## Transition ⏲️ 

- [x] Podemos usarlo cuando algo cambia 
- [x] Retrasa el tiempo que toma de un estado a otro

```css
.elemento {
  background: blue;
  transition: background .5s;
}

.elemento:hover {
  background: red;
}
```
> Tomara medio segundo en cambiar de color


## KEYFRAMES 🔑​

> Usados para definir animaciones a aplicar cambios graduales a un elemento
> Podemos definir los estados entre una animación y su transformación
<br/>

> Usamos __@keyframes__ + el nombre que queramos poner a nuestra animación: 

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

> Ahora la aplicamos: 

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

```transform: skew(-42deg)```
```transform: rotate(-40deg)```

- [x] __Skew__

> Inclinamos hacia un eje la imagen


## BOX SHADOW

- [x] Está pensado para ponerle sombras a __CAJAS__ de elementos
- [x] El primer valor es el __offset__ en X 
- [x] El segundo valor es el __offset__ en Y
- [x] El tercer valor es el __blur__
- [x] El cuarto valor (_opcional_) es el __spread__


```css
.box-shadow{
  box-shadow: .75em .75em 1em;
}
```

## FILTER

- [x] Podemos crear __EFECTOS__ en el contenido de un elemento.

```css
.sombrita{
  filter: drop-shadow(.75em .75em 1em);
}

.varios{
   filter: blur(3px) drop-shadow(0.5em 0.75em 30px gray) opacity(0.5);
}
```
- [x] Colores

* Sepia, invert, grayscale
* Brightness, contrast, saturate

```css
 .bbm {background-image:
  url(star.svg),
  url(diamond.png);
  background-color: goldenrod;
  background-blend-mode: color-burn, luminosity;
}
```

### ISOLATION

- [x] Sustituye a __position:relative__ y __z-index:1__
- [x] Aisla el elemento
- [x] Evita que su HIJOS interfieran con el __z-index__ de otros elementos

```html
<div class="hero">
  <div class="hero-intro">
      <h1><code>mix-blend-model</code>
      is pretty awesome</h1>
      <p>Some of the blending modes might seem a little strange
          at first, but you can use them for some effects</p>
  </div>
</div>    
```

```css
.hero{
    background-image: url(https://images.unsplash.com/photo-1749497683202-d3073573d996?q=80&w=1247&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D);
    min-height: 100vh;
    color: white;
    background-size: cover;
    display:flex;
    isolation: isolate;
}

.hero-intro{
    width:40%;
    padding: 2em;
    /* Excelente para padding RESPONSIVO */
    padding-top: min(15vh, 10rem);
    position: relative;
}

.hero-intro::after{
    content:'';
    position: absolute;
    background: #355f08;
    inset:0;
    z-index:-1;
    mix-blend-mode: multiply;
}

code{
    display: block;
}
```
## Clip Path

- [x] __RECORTA__ el área visible de elementos
- [x] El elemento debe tener __DIMENSIONES__ 
- [x] __NO__ cambia el tamaño de sus dimensiones

### Sin recortar, pero redondeando las esquinas:

```css
div{width:400px;height:400px}
.element {
  background-color: orange;
  clip-path: inset(0px 0px 0px 0px round 10px);
}
```
### Recortes básicos (top, right, bottom, left):
  
```css
div{width:400px;height:400px}
.element {
  background-color: orange;
  clip-path: inset(100px 50px 100px 50px);
}
```
### Recortes Circular
  
```css
div{width:400px;height:400px}
.element {
  background-color: orange;
  clip-path: circle(50% at left); /* Default: Center */
}
```

### Recorte Poligonal

- [x] Cada par de 

```css
.element {
  background-color: orange;
  clip-path: polygon(50% 0, 0 100%, 100% 100%); /* Triángulo */
}
```

### Efectos con Clip Path

```css
.element {
  width: 100px;
  height: 100px;
  background: coral;
  clip-path: polygon(
    20% 0%, 80% 0%, 100% 20%, 
    100% 80%, 80% 100%, 20% 100%, 
    0% 80%, 0% 20%
  );
  transition: clip-path 0.5s ease;
}

.element:hover {
  clip-path: polygon(
    30% 10%, 70% 10%, 90% 30%, 
    90% 70%, 70% 90%, 30% 90%, 
    10% 70%, 10% 30%
  );
}
```
## Formas de crear un RECTANGULO

- [x] __1__

```css
.element {
  width: 200px;
  height: 100px;
  background-color: #007BFF;
}
```

## Formas de crear un CIRCULO

```css
.element {
  width: 100px;
  height: 100px;
  border-radius: 50%; 
  background-color: #007BFF;
}
```
- [x] Usando aspect-ratio

```css
.element {
  width: 150px;
  aspect-ratio: 1; 
  border-radius: 50%;
  background-color: #007BFF;
}
```
> __aspect-ratio__ se usa para mostrar proporción: ancho - alto <br/>
> por ejemplo, hacemos un rectángulo con __4/3__
> y para un video podría ser __16/9__

- [x] Con clip-path NO es necesario que el elemento sea cuadrado

```css
.element {
  width: 100px;
  aspect-ratio: 2 / 1; 
  background-color: orange;
  clip-path: circle(30%); 
}
```

```css
.element {
  width: 300px;
  aspect-ratio: 3 / 1; 
  background-color: orange;
  clip-path: circle(15%); 
}
```
- [x] Hacer el recorte desde un punto del elemento

```css
.element {
  width: 100px;
  aspect-ratio: 2 / 1;
  background-color: orange;
  clip-path: circle(10px at 60px 40px);
}
```
- [x] Usando Radial Gradient

```css
.element {
  width: 150px;
  aspect-ratio: 1;
  background-image: radial-gradient(circle, maroon 50%, transparent 50%);
}
```

- [x] Usando Box Shadow

```css
.element {
  width: 30px;
  aspect-ratio: 1;
  border-radius: 50%;
  background-color: #007BFF;
  box-shadow: 100px 20px 0 orange, 200px 50px 0 limegreen, 60px 100px 0 #FF3333;
}
```

## Formas de crear un TRIANGULO

- [x] Con __Clip Path__

```css
.element {
    width: 100px;
    height: 100px;
    background: orange;
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}
```
- [x] Con __Linear Gradient__

```css
.element {
  width: 100px;
  height: 100px;
  background: linear-gradient(45deg, transparent 50%, royalblue 0);
}
```

- [x] Con __Conic Gradient__

```css
.element {
  width: 100px;
  height: 100px;
  background: conic-gradient(from -45deg,orange 90deg, royalblue 0, royalblue 180deg, red 0, red 270deg, green 0);
}
```

> Ahora quitamos los demas colores:

```css
.element {
  width: 100px;
  height: 100px;
  background: conic-gradient(from -45deg,orange 90deg, transparent 0);
}
```
- [x] Usando Unicode de __triángulo__

```css
<div>▴</div>
<style>
  div {
    color: orange;
    font-size: 10rem;
  }
</style>
```

## Formas de crear un HEXAGONO

> Entendiendo el uso de border, creando un __triángulo__

```css
.element{  
  width: 0;
  height: 0;
  border-left: 50px solid transparent;  
  border-right: 50px solid transparent; 
  border-bottom: 100px solid red;
}
```

- [x] Por medio de __bordes__ y __pseudoelementos__:

```css
.element {
  position: relative;
  width: 300px;
  height: 173.2px;
  background-color: #007BFF;
  margin: 86.6px 0;
}

.element::before {
  content: "";
  position: absolute;
  width: 0;
  border-left: 150px solid transparent;
  border-right: 150px solid transparent;
  bottom: 100%;
  border-bottom: 86.6px solid #007BFF;
}

.element::after {
  content: "";
  position: absolute;
  width: 0;
  border-left: 150px solid transparent;
  border-right: 150px solid transparent;
  top: 100%;
  width: 0;
  border-top: 86.6px solid #007BFF;
}
```
- [x] Por medio de __Clip Path__

```css
.element {
  width: 300px;
  height: 300px;
  background: cadetblue;
  -webkit-clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
  clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
}
```

## MASK

> Aplicamos sobre una imagen:

```css
img.masked {mask-image: url(theatre-masks.svg);}
```

## Cursor ✋🏼 

> Para cambiar el aspecto del puntero del mouse a: <br/>
> pointer, crosshair, e-resize, grab, help, move, 
> progress, text, wait, no-allowed, no-drop 

# GRADIENTS

- [x] __LOS GRADIENTES SON IMÁGENES__
- [x] __SON TRANSFORMACIONES VISUALES DE UN COLOR A OTRO__
- [x] __LA TRANSICION DEPENDE DEL ESPACIO Y PUNTOS DEFINIDOS__

## Linear Gradient

- [x] La dirección básica que corre un gradiente es de __arriba a abajo__
- [x] Arriba a abajo equivale a __180deg__
- [x] Deben contener __DOS COLORES__, aunque pueden ser el mismo


```css
#ex01 {background-image: linear-gradient(purple, gold);}
#ex02 {background-image: linear-gradient(90deg, purple, gold);}
#ex03 {background-image: linear-gradient(to left, purple, gold);}

```

- [x] Por Default, un gradiente toma __TODO__ el espacio disponible

```css
 div {
  background-image:
  linear-gradient(to top, transparent 1vw, rgba(0 0 0 / 0.2) 1vw),
  linear-gradient(to right, transparent 1vw, rgba(0 0 0 / 0.2) 1vw);
  background-size: 2vw 2vw;
  background-repeat: repeat;
 }
 
 div.fruit {background-color: papayawhip;}
 div.grain {background-color: palegoldenrod;}
 div.fishy {background-color: salmon;}
```

## Radial Gradient

```css
.radial {background-image: radial-gradient(50px, purple, gold)}
.radial {background-image: radial-gradient(50px 100px, purple, gold)}
```

```css
div{
  background: radial-gradient(darkturquoise 75%, hotpink 75%)
}
```

* Crear un "__anillo__" color rosa

```css
div{
  background: radial-gradient(white 65%, hotpink 65%);
  border-radius: 50%;
}
```

* Crear un efecto de círculos __repetidos__

```css
div{
  background: repeating-radial-gradient(darkturquoise 0px, darkturquoise 20px, hotpink 20px, hotpink 40px)
}
```

* Crear otro efecto de círculos __esquinados__

```css
div{
  background: repeating-radial-gradient(farthest-corner at 0 0, violet, violet 75px, palegreen 75px, palegreen 150px)
}
```

## Conic Gradient

> Para degradado suave, el ultimo y primer color deben __coincidir__

```css
.bk1{
  background: conic-gradient(black, gray, black, white, black, silver, black)
}
.bk2{
  background: conic-gradient(from 144deg, black, gray, black, white)
}
.bk3{
  background: conic-gradient(from 144deg at 3em 6em, black, gray, black, white)
}

 .hues {
  height: 10em; width: 10em;
  background: conic-gradient(red, magenta, blue, aqua, lime, yellow, red);
 }
 
 #wheel {
  border-radius: 50%;
 }
```
```<div class="hues"></div>```
```<div class="hues" id="wheel"></div>```

```css
.bk5{
  background:  conic-gradient(green 35%, yellow 40% 60%, red 65%);
}
```


# RESPONSIVE DESIGN 🦎

## Media Queries 

> Es una forma de adaptar contenido a diferentes pantallas

```css
@media (min-width: 768px){
  /* CSS only for screens below or equal to 600px width */
}

@media (min-width: 1200px){
  /* CSS only for screens below or equal to 600px width */
}
```
<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

# Flexbox 🦎

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

1. Necesitamos una clase padre para contener **flexbox**:

```css
.container{
  display: flex;
  gap: 1rem; 
}
```
> Gap es el **espacio** entre elementos

2. Necesitamos al menos un elemento hijo

3. Necesitamos agregar la **dirección** en el contenedor con **flex-direction**:

```css
.container{
  display: flex;
  flex-direction: column; /* Por default: row */
  gap: 1rem; 
}
```
- [x] No veremos nada hasta agregar elementos y contenido
- [x] Por Default, se crea un bloque que ocupa TODO el ancho
- [x] Los elementos se van acomodando uno al lado del otro

## Cambiar la base

> La **base** es el eje que elegimos con **flex-direction**

- [x] Podemos cambiar el tamaño de cada elemento en esa dirección con:

```css
.container > *{
  flex-basis: 100px;
}
```

- [x] Debemos agregar __flex-basis__ al elemento HIJO.

## Envolver elementos

> Por default, los elementos son **nowrap**
> Para que se envuelvan debemos agregar al elemento padre:

```css
flex-wrap: wrap;
```

## Orden de elementos

> Podemos cambiar el orden de los elementos con:

```css
.first{
  order: 10; 
  /* Será desplegado en segundo lugar */
}

.second{
  order: 0; 
  /* Será desplegado en primer lugar */
}
```

## Justificar elementos

> Es la alineación del **EJE PRINCIPAL**

```justify-content:flex-start```

* flex-start 
* flex-end 
* center
* space-between 
* space-around
* space-evenly
<br/>

## Alinear Contenido

> Es la alineación de toda la caja del **EJE SECUNDARIO**

```align-content:flex-start```

* flex-start
* flex-end
* center 
* stretch 
* space-between
* space-around
* space-evenly
  
## Place Content

```place-content:flex-start```

> Es la forma corta de usar __align-content__ y __justify-content__ a la vez


## Alinear Items

> Es la alineación de los elementos dentro de su __propia caja__

```align-items:flex-start```

* flex-start
* flex-end
* center 
* baseline
* stretch 

<strong style="color:ff004d">
Para ver como funciona, agregamos al padre:
</strong>

```css
.padre{
  height: 70vh;
}
```

## Align Self

> Para alinear __SOLO__ un elemento

```css
.elemento{
  align-self: flex-end; 
}
```

## Tamaño de elementos

```css
.elemento{
  flex-grow: 0;
  flex-shrink: 0;
}
```

## Centrar elementos

```css
.elemento{
  display: flex;
  justify-content: center;
  align-items: center;
}
```

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

# GRID 🦎

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

> Es la mejor forma de crear diseños complejos de diferentes tamaños

> De cierta manera, se mueven los elementos como **tetris**

1. También necesitamos una clase padre para contener un Grid Layout:

```css
.grid-layout{
  display: grid;  
}
```

2. Debemos indicar cuantas filas y columnas necesitamos:

- [x] Cada **valor** representa una columna


```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```


<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>


# CSS Hacks

- [x] Hacer el código __MANTENIBLE__

> Si queremos crear un borde de 10px excepto a la izquierda, 
> pensarías que es sensato poner:

```border-width: 10px 10px 10px 0;```

> Pero tendríamos que modificar __3__ valores si queremos una modificación, 
> por lo que es una mejor práctica escribir:

```css
border-width: 10px;
border-left-width: 0;
```

- [x] Crear botones brillosos

> Esta práctica ademas nos ayuda a cambiar de color de un botón
> tan solo __sobreescribiendo__ el background-color.

```css
button{
 padding: .3em .8em;
 border: 1px solid rgba(0,0,0,.1);
 background: #58a linear-gradient(hsla(0,0%,100%,.2), 
                                 transparent);
 border-radius: .2em;
 box-shadow: 0 .05em .25em rgba(0,0,0,.5);
 color: white;
 text-shadow: 0 -.05em .05em rgba(0,0,0,.5);
 font-size: 125%;
 line-height: 1.5;
}

button.cancel {
 background-color: #c00;
}

button.ok {
 background-color: #6b0;
}
```


<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>