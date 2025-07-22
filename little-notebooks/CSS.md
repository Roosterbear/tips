<h1 style="color:#AE445A">CSS</h1>

- [HTML Básico](#html-básico)
- [Etiquetas HTML5](#etiquetas-html5)
- [Formularios](#formularios)
- [Tablas](#tablas)
- [CSS Básico](#css-básico)
- [ESPECIFICIDAD](#especificidad)
- [FUENTES](#fuentes)
  - [Line Height](#line-height)
- [IMAGENES](#imagenes)
- [MEDIDAS](#medidas)
  - [Keywords](#keywords)
  - [Global Keywords](#global-keywords)
- [BOXES](#boxes)
- [FONDOS](#fondos)
  - [Fondo Fijo](#fondo-fijo)
- [SELECTORES](#selectores)
  - [Hijo](#hijo)
  - [Descendiente](#descendiente)
  - [Adyacente](#adyacente)
  - [Selectores de Atributo](#selectores-de-atributo)
- [POSICIONAMIENTO](#posicionamiento)
  - [Static](#static)
  - [Relative](#relative)
  - [Absolute](#absolute)
  - [Fixed](#fixed)
  - [Sticky](#sticky)
  - [Menu con Float](#menu-con-float)
- [DISPLAY](#display)
  - [Block](#block)
  - [Inline](#inline)
  - [Inline-block](#inline-block)
  - [None](#none)
- [CENTRADO](#centrado)
  - [Centrar un elemento](#centrar-un-elemento)
  - [Centrar un texto](#centrar-un-texto)
  - [Centrar Bloques](#centrar-bloques)
  - [Centrado Vertical](#centrado-vertical)
- [VARIABLES](#variables)
  - [Asignar variables](#asignar-variables)
  - [Usar variables](#usar-variables)
- [CAMBIO DE ELEMENTOS 🦋 ](#cambio-de-elementos-)
  - [Pseudoelementos](#pseudoelementos)
  - [Radius 🔘 ](#radius-)
  - [Transition ⏲️ ](#transition-️)
  - [KEYFRAMES 🔑​](#keyframes-)
  - [BOX SHADOW](#box-shadow)
  - [FILTER](#filter)
  - [Radial Gradient](#radial-gradient)
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
  - [Cursor ✋🏼 ](#cursor-)
- [RESPONSIVE DESIGN 🦎](#responsive-design-)
  - [Media Queries](#media-queries)
- [Flexbox 🦎](#flexbox-)
  - [Cambiar la base](#cambiar-la-base)
  - [Envolver elementos](#envolver-elementos)
  - [Orden de elementos](#orden-de-elementos)
  - [Justificar elementos](#justificar-elementos)
  - [Alinear elementos](#alinear-elementos)
  - [Tamaño de elementos](#tamaño-de-elementos)
  - [Centrar elementos](#centrar-elementos)
- [GRID 🦎](#grid-)
- [CSS Battle](#css-battle)


<div style="color:#219ebc">

# HTML Básico
</div>

- [x] Todo lo que vemos en una página web, está mostrado en __HTML__
- [x] Es un lenguaje basado en __etiquetas__
- [x] Generalmente las etiquetas van en pares (__apertura__ y __cierre__)
- [x] Como estándar, las páginas comienzan con:

```html
<!DOCTYPE html>
<html>

</html>
```
- [x] Dentro de html, tenemos 2 secciones importantes: __head__ y __body__
- [x] En el __head__ ponemos las configuraciones
- [x] En el __body__ va todo el contenido

* En el __```<head>```__ podemos incluir:

- [x] El título de la página

```<title>Mi sitio web</title>```

- [x] Metadata:

```<meta charset="utf-8">```
```<meta name="viewport" content="width=device-width, initial-scale=1.0">```
```<meta name="description" content="Tienda de articulos para perros">```

- [x] Etiqueta __link__ para relacionar el documento con recursos __externos__

* Para agregar archivos __CSS__:

```html
<link rel="stylesheet" href="styles.css" />
```
* Para definir el ícono del sitio:

```html
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

* Para agregar fuentes:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
```

* Para agregar alternativas de código:

```html
<link rel="alternate" hreflang="es" href="https://ejemplo.com/es/" />
<link rel="alternate" hreflang="en" href="https://ejemplo.com/en/" />
```

<div style="color:#219ebc">

# Etiquetas HTML5
</div>

- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces
- [x] Enlaces

<div style="color:#219ebc">

# Formularios
</div>

<div style="color:#219ebc">

# Tablas
</div>
  
<div style="color:#AE445A">

# CSS Básico
</div>

- [x] Limpiar propiedades

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

- [x] Dar formato a las fuentes de todo el cuerpo

```css
body{
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
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


# ESPECIFICIDAD

0. __!important__ Anula todo lo demás: ```p{color:red !important}``` 
1. __Estilos en línea__ Tiene el máximo grado de valor, como: ```<p style="color:green">Hola</p>``` 
2. __Selectores ID__ Segundo grado de valor: ```#principal``` 
3. __Clases__ Tercer grado de valor: ```.my-class``` 
4. __Elementos / Pseudoelementos__ Cuarto grado de valor: ```div``` ```p``` ```::before``` 

- [x] Debemos tomar en cuenta:

1. Como se van recibiendo las propiedades, se van cambiando:

```css
li{
  color: red;
  color: blue;
}
```
> En este caso, el color sera __AZUL__
> **Se LEE de arriba hacia abajo**
> Primero recibimos ROJO, pero __lo cambiamos__ por AZUL


2. Después de los estilos en línea, el código en la **CABECERA** tiene el __segundo__ grado de prioridad

```<style> /* code */<style>```  

3. El código dentro de un __css__ externo es el que tiene __menos__ prioridad


# FUENTES

* _px_ Medida estándar. **NO ESCALABLE**, usar solo para medidas **FIJAS**
* _em_ Medida para fuentes, equivale a la letra M del elemento padre

- [x] __Utilizarlos para íconos y botones__
- [x] __Media Queries__ porque respeta preferencias del __zoom__ en navegador

```css
.card {
  font-size: 16px;
  padding: 1em; /* 16px */
}
.card-button {
  font-size: 0.8em; /* 16px * 0.8 = 12.8px */
}
```

* _rem_ Basada en la fuente raíz del HTML

- [x] Usarlos para __tamaños de fuentes__, __márgenes__, __paddings__ y __dimensiones__.

```css
  p{
    font-size: 62.5%; 
  }
```
> 1rem AHORA es de 10px ❗

## Line Height

> Puede ser en proporción o con alguna medida:

```css
font-size: 20px;
line-height: 30px;
```

> __Observa__ que el alto de la línea es 1.5 mayor que la fuente <br/>
> Podemos cambiar la altura a:

```css
font-size: 20px; /* De igual manera, podemos usar 125% con una fuente de 16px */
line-height: 1.5;
```

# IMAGENES

> Estas 2 propiedades nos ayudan a tener un mejor despliegue de una imagen:

```css
img{
  max-width: 100%;
  display: block;
}
```

# MEDIDAS

## Keywords

> Usado para __valores__ que se describan con una palabra, por ejemplo:
<br/>

```a[href]{text-decoration:none}```

## Global Keywords

> Se aceptan de manera general

__inherit__ <br/>

> Hace que el valor de la propiedad del elemento se el mismo que el padre.

<br/>

> En este ejemplo veremos más claro su uso, ya que por lo general, los estilos se van heredando a los hijos.

<br/>

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




# BOXES

> Los elementos en CSS tienen capas desde el centro al extremo
> El primer nivel es el mismo **contenido** 
> Podemos tener un **borde** afuera del contenido
> Este puede tener __color__ y __ancho__
> Entre el contenido y el borde hay un espacio en blanco llamado **padding**
> Entre el borde y la parte de afuera existe un espacio llamado **margin**


# FONDOS

```css
body{
  background-color: #ffffff;
  background-image: url(fruits.jpg);
  background-repeat: no-repeat;
  background-position: center center;
}
```
 > Podemos usar en **background-repeat:** no-repeat, repeat, repeat-x, repeat-y. 
 > En **background-position**, el primer **center** es para arriba y abajo
 > En **background-position**, el segundo **center** es para izquierda y derecha
 
 
## Fondo Fijo
 
 ```css
  background-attachment: fixed;
  background-size: cover;
  height: 95vh;
 ```
 
 > __cover__ se usa para adaptar el fondo a toda la imagen sin importar el DISPOSITIVO.
 

# SELECTORES

## Hijo

> Es una etiqueta **INMEDIATAMENTE** dentro de otra

```css
div > strong{
  color: red;
}
```

```html
<strong>This doesn't change color</strong>
<div><strong>This will be RED actually</strong></div>
```
> Solo afecta a la etiqueta **strong** dentro de un **div**

## Descendiente

> Es una etiqueta dentro de otra sin importar la **PROFUNDIDAD**

```css
div strong{
  color: green;
}
```

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

## Adyacente

> Una etiqueta **DESPUES** de otra

```css
p + p{
  text-indent: 1.5em;
}
```

## Selectores de Atributo

```css
a[href ^ = "#"]{  /* Comienza con...*/
  color: red; 
}

a[href * = "#"]{  /* Contiene...*/
  color: red; 
}


a[href $ = "#"]{  /* Termina con...*/
  color: red; 
}
```

<br/>

# POSICIONAMIENTO

## Static

> Toma los valores por default del elemento.
> No se mueve de su posición original

```css
div{
  position: static;
}
```

## Relative

> Mueve su posición basándose en el contenedor: __top__ y __left__. 

```css
div{
  position: relative;
}
```

## Absolute

> Mueve su posición en relación al ancestro más cercano: 
> __top__ y __left__.
> Es necesario que el ancestro sea "relative" para que funcione.

```css
div{
  position: absolute;
}
```

## Fixed

> Posición relativa a la esquina superior izquierda del navegador. 
> Se pega como chicle y no se mueve con el scroll.

```css
div{
  position: fixed;
}
```

## Sticky

> Es una mezcla entre relative y fixed.

```html
<div class="table-container">
  <table>
    <thead>
      <tr><th>Nombre</th><th>Edad</th></tr>
    </thead>
    <tbody>
      <tr><td>Ana</td><td>25</td></tr>
      <!-- Más filas... -->
    </tbody>
  </table>
</div>
```

```css
.table-container {
  height: 200px; /* Limita el contenedor para que el sticky funcione */
  overflow: auto; /* Permite scroll interno */
}

th {
  position: sticky;
  top: 0; /* Encabezado pegado al hacer scroll vertical */
  background: #f1f1f1;
}
```

- [x] No funciona si el padre tiene __overflow:hidden__
- [x] Requiere un __offset__ como ```top``` o ```bottom``` para activarse
- [x] El contenedor padre debe tener una altura definida como: __height: 100vh__


## Menu con Float

```css
nav ul li{
  float: left;
  list-style: none; 
  margin: 10px;
}

.clearfix{
  clear: both; /* We have to include a div with this class after the menu */
}
```

# DISPLAY

## Block

* El elemento actúa como una caja
* Contiene Alto y Ancho
* Ocupa todo el ancho de la página
* El siguiente elemento se posiciona abajo

## Inline

* El elemento no contiene medidas
* El siguiente elemento se coloca a un lado

## Inline-block

* Permite que el elemento tenga __medidas__
* __NO__ agrega una nueva línea 

## None

> El elemento __DESAPARECE__
> Si queremos quitarlo sin eliminar el espacio que ocupa usamos:

```visibility:hidden;```

# CENTRADO

## Centrar un elemento

> Agregar padding:

```css
#features{
  padding: 7% 15%;
}
```
> 7% arriba y abajo
> 15% izquierda y derecha

> **ESTA MEDIDA ES PERFECTA PARA UNA SECCION**

## Centrar un texto

> Agregar una clase y centrar como:

```css
.feature-box{
  text-align: center;
  padding: 5%;
}
```

## Centrar Bloques

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

## Centrado Vertical

> Ponemos **height** y **line-height** con el mismo valor 

```css
.box{
  text-align: center;
  height: 100px;
  line-height: 100px;
}
```

# VARIABLES

## Asignar variables

```css
:root{
  --primary-color: white;
}
```

## Usar variables

```css
p{
  color: var(--primary-color);
}
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

- [x] Podemos crear __SOMBRAS__ en el contenido de un elemento.

```css
.filter-shadow{
  filter: drop-shadow(.75em .75em 1em);
}
```

## Radial Gradient

- [x] Crea fondos de colores en forma circular

* Crear un __circulo__ turquesa dentro de otro color rosa

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

## ISOLATION

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

* Cómo dibujariamos un rectángulo sin contenido html?

> Podemos poner borde al body y hacer que se vea agregando padding:
```body{border:1px solid;padding:50px}```

* Cómo dibujar un cuadrado relleno de negro sin agregar etiquetas html?

> Podemos agregar un cuadro con código __unicode__
> y crecerlo con ```zoom:10```
```&#x220E```

* Cómo dibujaríamos un rectángulo sin usar width ni height?

```p{border:1px solid;padding:50px}```


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


## Cursor ✋🏼 

> Para cambiar el aspecto del puntero del mouse a: <br/>
> pointer, crosshair, e-resize, grab, help, move, 
> progress, text, wait, no-allowed, no-drop 


<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

# RESPONSIVE DESIGN 🦎

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

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
> No veremos nada hasta agregar elementos y contenido

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

## Alinear elementos

> Es la alineación del **EJE SECUNDARIO**

```align-items:flex-start```

<strong style="color:red;">

❗ SOLO FUNCIONA CON NO-WRAP ❗ 
</strong>

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
<strong style="color:#ff004d">
Para cambiar solo un elemento
</strong>

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

```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```
- [x] Cada **auto** o **valor** son una columna

3. Tamaño de un elemento:

```css
.box1{
  grid-column: 1/3;
}
```

- [x] Donde **1** es la primer linea (**no el espacio**❗).

```css
.box2{
  grid-row: span: 2;
}
```

4. Posición del elemento:

```css
.astronaut{
  background-color: #03989e;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 3;
}
```

> También podemos usar **grid-area** para poner 4 valores: 

```css
.cowboy{
  grid-area: 2 / 1 / 3 / 3; 
}
```
> Donde el orden es: 

1. grid-row-start 
2. grid-column-start 
3. grid-row-end and 
4. grid-column-end 


<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

  
<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>



<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

# CSS Battle

- [x] Quitar __espacios__ y comentarios
- [x] Omitir el __;__ final del CSS
- [x] No usar, por lo general, la etiqueta HTML de __cierre__
> (__OJO__: Con etiquetas iguales las tomaría como hijas de la anterior)
- [x] Usar __margin__ y __auto__ para centrar sobre posiciones relativas
- [x] Crear atributos propios de selectores ```<p a>``` ```p[a]{}```
- [x] Usar position __fixed__
- [x] Juega con __unidades__: 200px = __2in__ = __50vw__ (50% del lienzo)
- [x] No siempre tienes que agregar etiquetas, ya existe __html__ y __body__
- [x] No es necesario poner la unidad __px__
- [x] Usar: ```<body bgcolor=red>```
- [x] Utilizar ```style=zoom:2``` para ampliar la pagina a lo doble
- [x] Podemos usar unicode: ･⬤

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>