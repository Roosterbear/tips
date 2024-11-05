# MASTER EN REACT 39 Hrs.

## INTRODUCCIÓN

### Crear comentarios en REACT

> Debemos ponerlos entre llaves para decirle que es código JS
> Usar comentarios JS como: {/* Mi comentario */}

### Mostrar los elementos de un array

```jsx

const libros = ["Harry Potter", "Clean Code", "Hacking the Hacker"];

return(
  <>
    <h1>Listado de libros</h1>
    <ul>
    {
      libros.map((libro, indice)=>{
        return <li key={indice}>{libro}</li>;
      })
    }
    </ul>
  </>
)
```





```
```



















