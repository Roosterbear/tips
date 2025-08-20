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

- [x] Ejecutar con: ```node script.js```

# TIPOS DE DATOS

```ts
function saludar(nombre: string): string{
  return `Hola ${nombre} !!`;
}

console.log(saludar("Typescript"));
```


```ts
type Disco = {
  id: number,
  artista: string,
  nombre: string
}

const discoteca: Disco[] = [
  {id:1, artista:"Men I Trust", nombre:"Oncle Jazz"},
  {id:2, artista:"Bjork", nombre:"Post"},
]

discoteca.forEach(d=>{
  console.log(`El disco ${d.nombre} de ${d.artista} es el No. ${d.id}`);
});
```









