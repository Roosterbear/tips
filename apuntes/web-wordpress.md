# Wordpress

## Themes

1. Entramos a nuestra carpeta _public_
2. Vamos a __wp-content/themes/__
3. Podemos ver las carpetas de los temas existentes
4. Creamos una nueva carpeta con el nombre de nuestro __TEMA__
5. NO DEBE LLEVAR ESPACIOS NI CARACTERES ESPECIALES
6. Agregamos 2 archivos principales: __index.php__ y __style.css__
7. El archivo style nos sirve para poner datos del plugin:

```css
/*
  Theme Name: Mi Primer Tema
  Author: Roosterbear
  Version: 1.0
*/

```

## Plugins

> Se encuentran en la carpeta plugins
> Dentro de la carpeta wp-content
> Debemos ponerlo en una carpeta unica

```php
<?php 
/*
* Plugin Name: My Fucking Plugin
* Plugin URI: www.roosterbear.com
* Description: This plugin does nothing
* Author: Roosterbear
* Version: 0.1
* Licence: GPL2
*/  
?>
```

## Hooks


