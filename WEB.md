# ALL ABOUT WEB PROGRAMMING
## HTML, CSS, Basic JS, and Tools

# HTML

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

## Elemento
El elemento __HTML__ tiene 3 elementos: <br />
Etiqueta de Apertura - Contenido - Etiqueta de Cierre
```html
<p>Hola Mundo</p>
```

## Etiqueta
Las etiquetas no llevan texto ni cierre
```html
<br/>
```

## Atributos
Van dentro de las etiquetas para enriquecer el contenido de la misma. <br/>
```html
<div class="mi-clase">Hola</div>
```
Es una buena práctica usar comillas dobles para los nombres de los atributos, <br/>
además de separar las palabras con guiones.<br/>

## Tablas

__Etiquetas básicas__ <br/>
```html
<table>
  <tr>
    <td>Data</td>
  </tr>
</table>
```
Necesitamos crear un renglón nuevo con la etiqueta ```<tr>``` <br/>
pero solo podemos poner información dentro de etiquetas ```<td>``` <br/>

__Encabezados__ <br/>
En lugar de usar la etiqueta ```<td>``` usamos ```<th>```<br/>
 
__Seccionar una tabla__ <br/>
Podemos crear 3 secciones y darles otro aspecto con estilos gracias a las etiquetas: <br/>
Para encabezados: <br/>
```html
<thead>
```
Para contenido: <br/>
```html
<tbody>
```
Para pie de página: <br/>
```html
<tfoot>
```

__Juntar 2 columnas:__
```html
<td colspan="2">
```

__Juntar 2 filas:__
```html
<td rowspan="2">
```



## Botones de radio
Se recomienda utilizar el mismo atributo _name_ para agrupar los botones de radio. <br/>
Podemos diferenciarlos con el atributo _id_.<br/>
Para elegir uno seleccionado usamos el atributo ```checked=checked``` o ```checked=true```<br/>
Observa el siguiente código:
```html
<input type="radio" name="igual" id="radio1">Radio #1<br/>
<input type="radio" name="igual" id="radio2" checked="checked">Radio #2
```


---
# CSS

Existen 3 formas de agregar código CSS: <br/>

1.- Entre las etiquetas ```<head>``` y ```</head>```, agregando las etiquetas ```<style>``` y ```<style>```


__Cursor__ <br/>
pointer, crosshair, e-resize, grab, help, move, progress, text, wait, no-allowed, no-drop <br/>



