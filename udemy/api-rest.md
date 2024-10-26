# API RestFul

## INTRODUCCION

### API

> Application Programing Interface
> Funcionalidades que nos ofrece un TERCERO para
> interactuar mediante una capa de ABSTRACCIÓN


### REST

> Arquitectura para servicios HTTP


### RestFul

> Implementación de REST


### ¿Por qué implementarla?

> * Facilita el escalamiento
> * Desacopla a tu cliente
> * Promueve la COMUNICACION 
>   de diversas TECNOLOGÍAS
>   llega desde un punto de acceso
>   ya sea como un JSON o XML
> * Reduce los consumos del servidor
> * Uniformiza tu proyecto mediante pautas


### Desventajas

* Mas desarrollo
* Más esfuerzo en pruebas


## Recursos

> Son URIs para acceder a la API

Ejemplo:

> api.kodoti.com/user

* __users__ son los __RECURSOS__
* _api.kodoti.com/user_ es el __ENDPOINT__


### Reglas para crear RECURSOS

* Deben ser __SUSTANTIVOS__
* Deben estar en __PLURAL__
* __NO USAR VERBOS__
* No persistir información: __STATELESS__



## HTTP REQUEST

* Es una petición
* Solicitar algo a nuestra API
* Mediante el protocolo HTTP


### Partes de un REQUEST

1. __Header__ - Metadata como ids, agentes o tokens
2. __Body__ - Lo que se va a manipular (JSON)
3. __QueryString__ - Parámetros que forman parte de la URL



## HTTP RESPONSE

* Es la respuesta que esperamos
* Se acompaña del __STATUS CODE__


### Partes de un RESPONSE

1. __Header__ - Metadata del servidor al cliente
2. __Body__ - La información en JSON



## STATUS CODES

* __404__ Not Found
* __400__ Bad Request
* __500__ Internal Server Error
* __200__ 0k


## SEGURIDAD

### CORS

> Por seguridad los navegadores restringen
> el cruce de información entre dominios distintos

### Autenticación

> Es el proceso en el que el cliente
> se identifica con nuestra API
> por ejemplo: __JSON WEB TOKEN__


### Autorización

> Son los __PERMISOS__ que tiene el usuario
> Se protege mediante __ROLES__


### OAuth

> Es un framework que gestiona
> la autorización de usuarios

* Delega la autenticación a terceros
* Podemos a cierta información del usuario
* Autoriza acceso a aplicaciones de terceros

### Roles de OAuth

1. __Propietario__ - Google, Facebook, LinkedIn
2. __Cliente__ - Empresa que lo implementa
3. __Servidor de Recursos__ - API
4. __Servidor de Autenticación__ - Servidor que genera el TOKEN

















