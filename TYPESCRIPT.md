<h1 style="color:#219ebc">TYPESCRIPT</h1>

- [INTRODUCCIÓN](#introducción)
- [TIPOS DE DATOS](#tipos-de-datos)

# INTRODUCCIÓN

- [x] __Instalación__ <br/>

```npm install -g typescript```
```tsc -v```

* Al compilar __Typescript__ se convierte en un __Javascript__ <br/>
* Ahora creamos un archivo script.ts <br/>

- [x] __Iniciar un proyecto__

```tsc -init```

- [x] __Compilar__

```tsc script.ts -w```

* Se genera ahora un archivo __script.js__
* Al tener el proyecto inicializado en __Typescript__ buscará todos los archivos
* Con el parámetro __-w__ se actualizará el __.js__ al guardar el __.ts__.


# TIPOS DE DATOS

- [x] __Strings__

```ts
const str1: string = "Hola";
const str2: string = 'Mundo';
const str3: string = `${str1} ${str2}`;
```

- [x] __Numbers__

```ts
const n1: number = 1;
const n2: number = 1.1;
```









