# WEB

- [WEB](#web)
  - [CSS](#css)
    - [Agregar CSS en HTML](#agregar-css-en-html)
    - [Limpiar propiedades](#limpiar-propiedades)
    - [Cómo actúa CSS](#cómo-actúa-css)
  - [Autenticación con OAuth](#autenticación-con-oauth)
    - [Autenticación](#autenticación)
    - [Autorización](#autorización)



## CSS

### Agregar CSS en HTML

```html
<link rel="stylesheet" href="style.css">
```

### Limpiar propiedades

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;  
}
```

### Cómo actúa CSS

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


