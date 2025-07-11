<h1 style="color:#dda15e">WEB</h1>

- [Etiquetas HTML5](#etiquetas-html5)
- [Formularios](#formularios)
- [Tablas](#tablas)
- [CSS Básico](#css-básico)
- [ESPECIFICIDAD](#especificidad)
- [FUENTES](#fuentes)
  - [Centrar un elemento](#centrar-un-elemento)
  - [Centrar un texto](#centrar-un-texto)
  - [Centrar Bloques](#centrar-bloques)
  - [Centrado Vertical](#centrado-vertical)
- [IMAGENES](#imagenes)
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
- [VARIABLES](#variables)
  - [Asignar variables](#asignar-variables)
  - [Usar variables](#usar-variables)
- [BOXES](#boxes)
- [CAMBIO DE ELEMENTOS 🦋 ](#cambio-de-elementos-)
  - [Pseudoelementos](#pseudoelementos)
  - [Radius 🔘 ](#radius-)
  - [Transition ⏲️ ](#transition-️)
  - [KEYFRAMES 🔑​](#keyframes-)
  - [BOX SHADOW](#box-shadow)
  - [FILTER](#filter)
  - [Radial Gradient](#radial-gradient)
  - [ISOLATION](#isolation)
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

<div style="color:#219ebc">

# Etiquetas HTML5
</div>


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

> _px_ Medida estándar. **NO ESCALABLE**, usar solo para medidas **FIJAS**
> _em_ Medida para fuentes, equivale a la letra M del elemento padre

- [x] __Utilizarlos para que un elemento escale en proporción a su fuente__
- [x] Usarlos en __Media Queries__ porque respeta preferencias del zoom en el navegador

```css
.card {
  font-size: 16px;
  padding: 1em; /* 16px */
}
.card-button {
  font-size: 0.8em; /* 16px * 0.8 = 12.8px */
}
```

> _rem_ Basada en la fuente raíz del HTML

- [x] Usarlos para __tamaños de fuentes__, __márgenes__, __paddings__ y __dimensiones__.

```css
  p{
    font-size: 62.5%; 
  }
```
> 1rem AHORA es de 10px ❗


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


# IMAGENES

> Estas 2 propiedades nos ayudan a tener un mejor despliegue de una imagen:

```css
img{
  max-width: 100%;
  display: block;
}
```

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

# BOXES

> Los elementos en CSS tienen capas desde el centro al extremo
> El primer nivel es el mismo **contenido** 
> Podemos tener un **borde** afuera del contenido
> Este puede tener __color__ y __ancho__
> Entre el contenido y el borde hay un espacio en blanco llamado **padding**
> Entre el borde y la parte de afuera existe un espacio llamado **margin**


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

## Radius 🔘 

> Para redondear una foto o elemento podemos agregar:

```css
img{
  border-radius: 50%;
}
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
- [x] Evita que su HIJOS interfieran con el z-index de otros elementos fuera del contenedor

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

```transform: skew(-42deg)```
```transform: rotate(-40deg)```
```nth-child()```
  
<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>


