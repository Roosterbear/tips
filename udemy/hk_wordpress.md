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


