# SEO

## Primeros Pasos

### Dominio

* Usar __Namecheap__ o _GoDaddy_
* Nombre exacto y __sonoro__
* No usar guiones de ningun tipo


### Hosting

* Usar CIMA Server
* Que tenga instalador de Wordpress


### Indexar a Google

* Buscar el dominio en google como: _site:misitio.com_


### Site Map

> Activarlo desde caracteristicas del YOAST SEO
> Verlo como misitio.com/sitemap_index.xml (o misitio.com/sitemap.xml)


### Robots.txt

> Es un archivo de texto plano, por default contiene:

```txt
User-agent: *
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php
```

* Debemos crear el archivo robots.txt en la raíz del sitio
* Agregarle TODOS los sitemaps con ruta __absoluta__

```txt
sitemap:  https://misitio.com/post-sitemap.xml
sitemap:  https://misitio.com/page-sitemap.xml
sitemap:  https://misitio.com/category-sitemap.xml
```


### Redirección

* Utilizar el plugin __redirection__


### Google Analytics

1.- Crear cuenta
2.- Meter codigo en nuestro header del sitio web


## SEARCH CONSOLE

> Ir a searchconsole.cc
> By prefix: Agregamos codigo en el head de nuestro index.html

* Agregar en Search Console nuestro dominio
* En Métodos alternativos de Search Console copiar el ID de la etiqueta HTML
* Pegarlo en Yoast: SEO - General - Webmaster Tools - __Código de Verificacion de Google__
* Agregar ruta Sitemaps a Search Console en: Indexación - Sitemaps - __Añadir o Probar Sitemap__



