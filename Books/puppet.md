# Pro Puppet

- [Pro Puppet](#pro-puppet)
  - [Introducción](#introducción)
  - [Instalación](#instalación)
  - [Manifiesto](#manifiesto)
    - [Problemas con librerías de Ruby](#problemas-con-librerías-de-ruby)

## Introducción

> Puppet se despliega bajo el modelo **cliente-servidor** <br/>
> Usa los servicios web **XML-RPC** sobre HTTPS en el puerto **8140** <br/>

- [x] El servidor se llama **Puppet master**
- [x] El cliente se le llama **agente**

## Instalación

- [x] Instalar Puppet master en Linux

```bash
apt-get install puppet puppetmaster
```
> Para agentes, solo instalar **puppet**

- [x] Instalar agente en Windows

[Descargar](http://downloads.puppetlabs.com/windows/)


## Manifiesto

> Un manifiesto tiene la forma tipo:

```json
Recurso { Nombre:
Atributo => Valor,
}
```
> Por ejemplo:

```json
file { '/tmp/hello':
content => "Hello, world\n",
}
```
* **Recurso:** Es un archivo
* **Nombre:** Es la ruta a ese archivo
* **Atributo:** Su atributo es contenido
* **Valor:** El valor de contenido será "Hola mundo"

> Entonces sucede lo siguiente:

1. Checa si existe el recurso en el servidor, sino Puppet lo crea
2. Checa el valor de cada atributo
3. Si el valor esta vacío o contiene otra cosa, Puppet lo sobreescribe

### Problemas con librerías de Ruby

- [x] Instalar RVM

```bash
\curl -sSL https://get.rvm.io | bash -s stable
```

- [x] Cargar RVM en la terminal

```bash
source ~/.rvm/scripts/rvm
```

- [x] Listar versiones de Ruby disponibles

```bash
rvm list known
```

- [x] Actualizar una librería con **gem**

```bash
gem update stringio
```
