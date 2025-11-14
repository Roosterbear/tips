<h1 style="color:#AE445A">CSS</h1>

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

# CUSTOM PROPERTIES

```css
html {
  --base-color: #639;--highlight-color: #AEA;
}

h1 {color: var(--base-color);}
h2 {color: var(--highlight-color);}
```
# Transition ⏲️ 

```css
.elemento {
  background: blue;
  transition: background .5s;
}

.elemento:hover {
  background: red;
}
```
# KEYFRAMES 🔑​

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

# BOX SHADOW

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

# Media Queries 🦎


```css
@media (min-width: 768px){
  /* CSS only for screens below or equal to 600px width */
}

@media (min-width: 1200px){
  /* CSS only for screens below or equal to 600px width */
}
```

# Flexbox 🦎

```css
.container{
  display: flex;
  flex-direction: column; /* Por default: row */
  gap: 1rem; 
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

# GRID 🦎

```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```