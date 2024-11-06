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

### Petición AJAX con fetch y promesas

```jsx
{/* PONEMOS EL ESTADO COMO UN OBJETO VACÍO */}
const [usuarios, setUsuarios] = useState([]);

const getUsuariosAjaxPms = ()=>{
  fetch("https://reqres.in/api/users?page=1")
    .then(respuesta=> respuesta.json())
    .then(
      resultado_final =>{
        setUsuarios(resultado_final.data);
        console.log(usuarios)
      },
      error =>{
        console.log(error);
      }
    );
}

useEffect(()=>{
  getUsuariosAjaxPms();
},[])
```


### Petición AJAX con Async y Await

```jsx
{/* PONEMOS EL ESTADO COMO UN OBJETO VACÍO */}
const [usuarios, setUsuarios] = useState([]);

{/* AQUI ES MUY IMPORTANTE USAR ASYNC PARA USAR AWAIT */}
const getUsuariosAjaxAW = async()=>{
  const peticion = await fetch("https://reqres.in/api/users?page=1");
  const {data} = await peticion.json();
}

useEffect(()=>{
  getUsuariosAjaxAW();
},[])
```

















