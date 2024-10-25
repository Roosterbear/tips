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

## Functions

> Editamos el index.php de nuestro plugin
> Podemos crear nuevas funciones o usar funciones de Wordpress

```php
<?php
function greet($name){
  echo "<p>Hola $name, bienvenido a Wordpress </p>";
}

// funciones propias
greet('Jacinto');
greet('Jeremias');

// funciones de Wordpress
bloginfo('name');
bloginfo('description');

?>
```


## Hooks








# Seguridad en Wordpress


## Quitar wp-admin

* Instalar plugin __WPS Hide Login__


## Prefijo Bases de Datos

* Al instalar Wordpress, cambiar prefijo: r00_


## Servicio CDN

* Agregar __Cloudflare__


## Wordfence

> Son de las cosas más importantes que hay que instalar

* Detecta fallos de seguridad


## Quitar Editor de archivos de temas

> En Apariencia se encuentra esta opción, debemos quitarla con:

```php
define('DISALLOW_FILE_EDIT', true);
define('DISALLOW_FILE_MODS', true);
```
> Esto se edita en el wp-config.php


## Quitar versiones de Wordpress

> Agregar el siguiente código en el wp-config.php

```php
remove_action('wp_head','wp_generator');
```


## Eliminar FEED y RSS

> Se pueden utilizar para scrapear contenido
> Si no se usan, es mejor deshabilitarlos 

```php
function itsme_disable_feed(){
  wp_die(__('No feed, visit: <a href="'.esc_url(home_url('/')).'">home</a>'));
}

add_action('do_feed','itsme_disable_feed',1);
add_action('do_feed_rdf','itsme_disable_feed',1);
add_action('do_feed_rss','itsme_disable_feed',1);
add_action('do_feed_rss2','itsme_disable_feed',1);
add_action('do_feed_atom','itsme_disable_feed',1);
add_action('do_feed_rss2_comments','itsme_disable_feed',1);
add_action('do_feed_atom_comments','itsme_disable_feed',1);
```


