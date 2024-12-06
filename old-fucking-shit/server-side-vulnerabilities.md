# Server-side Vulnerabilities

## Path Traversal

> También conocido como _directory traversal_
> Permite LEER ARCHIVOS DEL SERVIDOR
> Imagina un sitio que carga una imagen:

```html
<img src="/loadImage?filename=218.png">
```

> La imagen probablemente esté en: /var/www/images/218.png
> por lo que podríamos acceder a algo más interesante con:
> https://insecure-website.com/loadImage?filename=../../../etc/passwd
> Y para un servidor Windows:
> https://insecure-website.com/loadImage?filename=..\..\..\windows\win.ini


```html

```

```html
```

```html
```

```html
```

```html
```