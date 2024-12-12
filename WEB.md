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
  - [HACKS❗❗❗](#hacks)
    - [Limpiar propiedades](#limpiar-propiedades)
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

# CSS

## Primeros Pasos

1. Dar formato a las fuentes de todo el cuerpo

```css

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




## HACKS❗❗❗


### Limpiar propiedades

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

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


