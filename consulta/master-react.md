# MASTER EN REACT

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


## PROYECTO

1. Crear una carpeta para nuestro proyecto
2. Ejecutar:
> npm init

3. Usar __bcrypt__
4. Usar __JWT__
5. Agregar la librería __moment__
6. Emplear __Formik__ y __Yup__ para formularios
7. __react-time_ago__ para mostrar mejor el tiempo





