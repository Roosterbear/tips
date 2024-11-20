# REACT DE CERO A EXPERTO 54 Hrs.

## INTRODUCCION

> Debemos tener instalado:

1. Visual Studio Code / ES7 Plugin / Simple REACT Snippets
2. Node.js
3. Git 
4. Chrome / REACT DevTools / REDUX DevTools
5. Postman
6. Mongo Compass
* Manten actualizado Node:

> curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

> REINICIA LA TERMINAL !!!
> Instala la version de Node deseada: nvm install 14.4.0.
> Cambia la version: nvm use --delete-prefix v20.18.0



## JAVASCRIPT BASICO

> El Prototype es como el ADN de un OBJETO
> Crear CLON de un objeto: const persona2 = {...persona};


## PRIMERA APLICACION

* Usar __CRA__ para proyectos sencillos
* Usar __Vite__ para proyectos PROFESIONALES
* Usar __npm__ para dependencias GLOBALES
* Usar __yarn__ para dependencias LOCALES

1. Instalar con Vite:
> yarn create vite

2. Nos pedira informacion del proyecto. Poner nombre y en React con JS.
3. Entrar a la __CARPETA DEL PROYECTO__ y abrirla en VSC

> OBSERVACION: Ambos crean un proyecto tipo __NODE__


## DIFERENCIAS ENTRE CRA Y VITE

### CREATE-REACT-APP

1. Crea un __package-lock.json__ que nos dice como se originó el proyecto.
2. __.gitignore__ para indicar lo que no queremos que se suba a GIT o Github
3. __package.json__ con info del proyecto, scripts y dependencias
> Por ejemplo, tenemos los scripts para levantar el servidor de desarrollo,
> construye la version de producción con tree-shaking, pruebas y el eject (NO USAR)
4. __README.md__ lo que queremos mostrar en Github, Bitbucket, etc.
5. __PODEMOS VISUALIZARLO CON VSC__ como Markdown: Open Preview
6. La carpeta __node_modules__ de las cuales casi ninguna llega a __PRODUCCIÓN__
7. En public nos encontramos con el __manifest.json__ que es para una __PWA__
8. En __index.html__ es donde se montará la Single Page Application

* __LOS ARCHIVOS .lock NOSE MANIPULAN!__

### Vite

* __TIENE MENOS DEPENDENCIAS__
* __ES MEJOR EL HOT RELOAD__
* El index.html esta en raíz
* No hay una carpeta 
* No tiene un README.md
* No tiene un robots.txt
* No tiene un manifest.json
* INLUYE un vite.config.js
* INLUYE un yarn.lock
* Utiliza archivos .jsx











