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

