# Securing PHP Applications

- [Securing PHP Applications](#securing-php-applications)
  - [Introducción](#introducción)
    - [SEGURIDAD A TRAVÉS DE OSCURIDAD](#seguridad-a-través-de-oscuridad)

## Introducción

- [x] **UNA APLICACIÓN PUEDE SER UNA ENTRADA A TODA NUESTRA INFRAESTRUCTURA**

### SEGURIDAD A TRAVÉS DE OSCURIDAD

> Algunos programadores crean una complicada estructura de directorios
> y nombres de archivos sin sentido esperando confundir a los hackers

<br/>

> Lo que realmente hace un Hacker es ejecutar scripts que hagan el trabajo

- [x] Podemos probar con cambiar las extensiones de .php a .html
> Asegúrate que tu servidor procese los archivos .html como .php:

```bash
AddType application/x-httpd-php .html .htm
```

- [x] Podemos usar la función **moveFile()** si necesitamos mover archivos:

```bash
moveFile($filename, $tempPath = '/usr/local/bin/', $finalPath = '/www/');
```

- [x] Utilizar funciones seguras en PHP:

1. **VALIDACION Y SANITIZACIÓN DE DATOS**

  - [x] filter_var()
  - [x] htmlspecialchars()
  - [x] strip_tags()

2. **MANEJO DE ARCHIVOS**

  - [x] fopen(), fread(), fwrite(), fclose()
  - [x] file_get_contents(), file_put_contents()

3. **SESIONES Y COOKIES**

  - [x] session_star()
  - [x] set_cookie()

4. **ENCRIPTACIÓN Y HASHING**

  - [x] password_hash(), password_verify()
  - [x] openssl_encrypt(), openssl_decrypt()

5. **FUNCIONES DE RED**

  - [x] curl_init(), curl_setopt(), curl_exec(), curl_close()

6. **PHP DATA OBJECTS**





