# WEB

- [WEB](#web)
- [HTML](#html)
  - [Agregar CSS en HTML](#agregar-css-en-html)
- [CSS](#css)
  - [Primeros Pasos](#primeros-pasos)
  - [Cómo actúa CSS](#cómo-actúa-css)
  - [FUENTES](#fuentes)
  - [CENTRAR](#centrar)
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
    - [Pseudo-elementos](#pseudo-elementos)
    - [Pseudo-classes](#pseudo-classes)
  - [POSICIONAMIENTO](#posicionamiento)
    - [Static](#static)
    - [Relative](#relative)
    - [Absolute](#absolute)
    - [Fixed](#fixed)
    - [Menu con Float](#menu-con-float)
  - [VARIABLES](#variables)
    - [Asignar variables](#asignar-variables)
    - [Usar variables](#usar-variables)
  - [BOXES](#boxes)
  - [CAMBIANDO ELEMENTOS 🦋 ](#cambiando-elementos-)
    - [Radius 🔘 ](#radius-)
    - [Transition ⏲️ ](#transition-️)
  - [KEYFRAMES 🔑​](#keyframes-)
    - [Cursor ✋🏼 ](#cursor-)
  - [RESPONSIVE DESIGN 🦎](#responsive-design-)
    - [Media Queries](#media-queries)
  - [Flexbox](#flexbox)
    - [Cambiar la base](#cambiar-la-base)
    - [Envolver elementos](#envolver-elementos)
    - [Orden de elementos](#orden-de-elementos)
    - [Justificar elementos](#justificar-elementos)
    - [Alinear elementos](#alinear-elementos)
    - [Tamaño de elementos](#tamaño-de-elementos)
    - [Centrar elementos](#centrar-elementos)
  - [GRID Layout @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@](#grid-layout-)
  - [CSS Art !](#css-art-)
    - [FONDO](#fondo)
    - [Cara](#cara)
    - [Boca](#boca)
    - [Oido](#oido)
    - [Nariz](#nariz)
    - [Ojos](#ojos)
    - [Cabello](#cabello)
  - [HACKS❗❗❗](#hacks)
    - [Hack para medida REM](#hack-para-medida-rem)
    - [Eliminar underline de un ENLACE](#eliminar-underline-de-un-enlace)
    - [Eliminar linea punteada alrededor de los ENLACES](#eliminar-linea-punteada-alrededor-de-los-enlaces)
    - [Cambiar ESPACIO entre letras](#cambiar-espacio-entre-letras)
    - [Agregar SANGRIA](#agregar-sangria)
    - [Quitar circulos negros de las LISTAS](#quitar-circulos-negros-de-las-listas)
  - [Autenticación con OAuth](#autenticación-con-oauth)
    - [Autenticación](#autenticación)
    - [Autorización](#autorización)


# HTML

## Agregar CSS en HTML

```html
<link rel="stylesheet" href="style.css">
```
<div style="color:#AE445A">

# CSS
</div>

## Primeros Pasos

1. Limpiar propiedades

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

2. Dar formato a las fuentes de todo el cuerpo

```css
body{
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
}
```

## Cómo actúa CSS

- [x] **Posición**

> Como se van recibiendo, se van cambiando las propiedades

```css
li{
  color: red;
  color: blue;
}
```
> En este caso, el color sera AZUL
> **Se LEE de arriba hacia abajo**
> Primero recibimos ROJO, pero lo cambiamos por AZUL

- [x] **Especificidad**

> Es el grado del SELECTOR

1. __id__ Tiene el máximo grado de valor, como: ```#principal``` 
2. __attribute__ Segundo grado de valor: ```li[draggable]``` 
3. __class__ Tercer grado de valor: ```.my-class``` 
4. __element__ Cuarto grado de valor: ```li``` 

- [x] **Tipo**

> Es el **LUGAR** en donde se pone el código.

1. El código mostrado **DENTRO** de etiquetas tiene PRIORIDAD:

```html
<div style=""> </div>
```
2. El código en la **CABECERA** tiene el segundo grado de prioridad

```<style> /* code */<style>```  

3. El lugar con **MENOS** prioridad es en un archivo **.css**

```html
<link rel="stylesheet" href="style.css">
```
  
- [x] Importancia

```css
li{
  color: red !important;
  color: blue;
}
```
> Con la etiquet **!important** tendrá más prioridad

## FUENTES

> _px_ Medida estándar. **NO ESCALABLE**, usar solo para medidas **FIJAS**
> _em_ Medida para fuentes, equivale a la letra M del elemento padre
> _rem_ Basada en la fuente raíz del HTML

## CENTRAR

### Centrar un elemento

> Agregar padding:

```css
#features{
  padding: 7% 15%;
}
```
> 7% arriba y abajo
> 15% izquierda y derecha

> **ESTA MEDIDA ES PERFECTA PARA UNA SECCION**

### Centrar un texto

> Agregar una clase y centrar como:

```css
.feature-box{
  text-align: center;
  padding: 5%;
}
```

### Centrar Bloques

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

### Centrado Vertical

> Ponemos **height** y **line-height** con el mismo valor 

```css
.box{
  text-align: center;
  height: 100px;
  line-height: 100px;
}
```

## IMAGENES

> Estas 2 propiedades nos ayudan a tener un mejor despliegue de una imagen:

```css
img{
  max-width: 100%;
  display: block;
}
```

## FONDOS

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
 
 
 ### Fondo Fijo
 
 ```css
  background-attachment: fixed;
  background-size: cover;
  height: 95vh;
 ```
 
 > __cover__ se usa para adaptar el fondo a toda la imagen sin importar el DISPOSITIVO.
 

## SELECTORES

### Hijo

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

### Descendiente

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

### Adyacente

> Una etiqueta **DESPUES** de otra

```css
p + p{
  text-indent: 1.5em;
}
```

### Selectores de Atributo

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

### Pseudo-elementos

* ::after 
* ::before 
* ::selection 
* ::first-letter 
* ::first-line 


### Pseudo-classes

* ::checked
* ::disabled
* ::enabled
* ::first-child
* ::focus
* ::hover
* ::nth-child
* ::nth-lastchild
* ::visited
<br/>

## POSICIONAMIENTO

### Static

> Toma los valores por default del elemento.
> No se mueve de su posición original

```css
div{
  position: static;
}
```

### Relative

> Mueve su posición basándose en el contenedor: __top__ y __left__. 

```css
div{
  position: relative;
}
```

### Absolute

> Mueve su posición en relación al ancestro más cercano: 
> __top__ y __left__.
> Es necesario que el ancestro sea "relative" para que funcione.

```css
div{
  position: absolute;
}
```

### Fixed

> Posición relativa a la esquina superior izquierda del navegador. 
> Se pega como chicle y no se mueve con el scroll.

```css
div{
  position: fixed;
}
```

### Menu con Float

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

## VARIABLES

### Asignar variables

```css
:root{
  --primary-color: white;
}
```

### Usar variables

```css
p{
  color: var(--primary-color);
}
```

## BOXES

> Los elementos en CSS tienen capas desde el centro al extremo
> El primer nivel es el mismo **contenido** 
> Podemos tener un **borde** afuera del contenido
> Este puede tener color y ancho
> Entre el contenido y el borde hay un espacio en blanco llamado **padding**
> Entre el borde y la parte de afuera existe un espacio llamado **margin**



## CAMBIANDO ELEMENTOS 🦋 

### Radius 🔘 

> Para redondear una foto o elemento podemos agregar:

```css
border-radius: 50%;
```

### Transition ⏲️ 

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

### Cursor ✋🏼 

> Para cambiar el aspecto del puntero del mouse a:
> pointer, crosshair, e-resize, grab, help, move, 
> progress, text, wait, no-allowed, no-drop 


## RESPONSIVE DESIGN 🦎 

### Media Queries 

> Es una forma de adaptar contenido a diferentes pantallas

```css
@media (min-width: 768px){
  /* CSS only for screens below or equal to 600px width */
}

@media (min-width: 1200px){
  /* CSS only for screens below or equal to 600px width */
}
```

## Flexbox 

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
  flex-direction: column; /* Or by default: row */
  gap: 1rem; /* Space between elements */
}
```
> No veremos nada hasta agregar elementos y contenido

### Cambiar la base

> La **base** es el eje que elegimos con **flex-direction**

- [x] Podemos cambiar el tamaño de cada elemento con:

```css
.container > *{
  flex-basis: 100px;
}
```

### Envolver elementos

> Por default, los elementos son **nowrap**
> Para que se envuelvan debemos agregar al elemento padre:

```css
flex-wrap: wrap;
```

### Orden de elementos

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

### Justificar elementos

> Es la alineación del **EJE PRINCIPAL**

```justify-content:flex-start```

* flex-start 
* flex-end 
* center
* space-between 
* space-around
* space-evenly
<br/>

### Alinear elementos

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

<small style="color:ff004d";>

To see how it works, we have to add to the parent:
</small>

```css
.padre{
  height: 70vh;
}
```

<strong style="color:#ff004d">

Para cambiar solo un elemento
</strong>

<br/>

```css
.elemento{
  align-self: flex-end; 
}
```

### Tamaño de elementos

```css
.elemento{
  flex-grow: 0;
  flex-shrink: 0;
}
```

### Centrar elementos

```css
.elemento{
  display: flex;
  justify-content: center;
  align-items: center;
}
```

## GRID Layout @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

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
- [x] Cada *auto* o *value* son una columna

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

<div style="color:#004225";>

## CSS Art !
</div>


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

<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

<div style="color:#ff004d";>

## HACKS❗❗❗
</div>

### Hack para medida REM

```html
  font-size: 62.5%; 
```
> 1rem AHORA es de 10px ❗

### Eliminar underline de un ENLACE

```css
a:hover{
  text-decoration: none; 
}
```
### Eliminar linea punteada alrededor de los ENLACES

```css
a{
  outline: none;
}
```

### Cambiar ESPACIO entre letras

```css
p{
  letter-spacing: .1rem; /* We can use negative numbers */  
}
```

### Agregar SANGRIA

```css
p{
  text-indent: 5px;
}
```

### Quitar circulos negros de las LISTAS

```css
ul{
  list-style-type: none; /* or shorthand: list-style: */
}
```
> Podemos usar: disc, circle, upper-roman, lower-latin, square.


<br/>
<br/>
⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​⭐​
<br/>
<br/>

## Autenticación con OAuth

### Autenticación

> Es el proceso de verificar la identidad de alguien y saber que 
> una persona o entidad es quien dice ser por medio de:

- [x] Contraseñas
- [x] Biometría
- [x] Tokens

### Autorización

> Es el proceso de administrar permisos a recursos 
> a una persona o entidad por medio de:

- [x] **Accesos** - Que alguien pueda acceder a un recurso
- [x] **Permisos** - Lo que a esa persona se le permite hacer con dicho recurso
- [x] **Roles** - Conjunto de permisos generalizados a funciones específicas 


