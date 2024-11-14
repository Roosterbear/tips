# COMPLETE REACT DEVELOPER 42 Hrs

## PROYECTO CRWN CLOTHING

1. npx create-react-app crwn-clothing
2. Entramos a la carpeta creada:
> cd crwn-clothing

3. La abrimos con VSC
4. En el componente App dejamos un hola mundo
5. Ejecutamos el proyecto:
> yarn start

6. Creamos objetos y los pasamos con __map__
7. Agregar sass:
> yarn add sass

```scss
.categories-container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.category-container {
  min-width: 30%;
  height: 240px;
  flex: 1 1 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid black;
  margin: 0 7.5px 15px;
  overflow: hidden;

  &:hover {
    cursor: pointer;

    & .background-image {
      transform: scale(1.1);
      transition: transform 6s cubic-bezier(0.25, 0.45, 0.45, 0.95);
    }

    & .category-body-container {
      opacity: 0.9;
    }
  }

  &.large {
    height: 380px;
  }

  &:first-child {
    margin-right: 7.5px;
  }

  &:last-child {
    margin-left: 7.5px;
  }

  .background-image {
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center;
  }

  .category-body-container {
    height: 90px;
    padding: 0 25px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border: 1px solid black;
    background-color: white;
    opacity: 0.7;
    position: absolute;

    h2 {
      font-weight: bold;
      margin: 0 6px 0;
      font-size: 22px;
      color: #4a4a4a;
    }

    p {
      font-weight: lighter;
      font-size: 16px;
    }
  }
}
```

> Categories

```json
[
  {
    "id": 1,
    "title": "hats",
    "imageUrl": "https://i.ibb.co/cvpntL1/hats.png"
  },
  {
    "id": 2,
    "title": "jackets",
    "imageUrl": "https://i.ibb.co/px2tCc3/jackets.png"
  },
  {
    "id": 3,
    "title": "sneakers",
    "imageUrl": "https://i.ibb.co/0jqHpnp/sneakers.png"
  },
  {
    "id": 4,
    "title": "womens",
    "imageUrl": "https://i.ibb.co/GCCdy8t/womens.png"
  },
  {
    "id": 5,
    "title": "mens",
    "imageUrl": "https://i.ibb.co/R70vBrQ/men.png"
  }
]

```

8. Utilizar __REACT ROUTE OUTLET__
9. Usar __FIREBASE__
10. Login en Google
11. Entrar a:
> https://firebase.google.com

12. __Go to console__
13. ADD Project
14. Agregar nombre tipo: crown-clothing-db
15. Continue
16. Deshabilitamos Google Analytics para hacerlo más sencillo
17. Lo que más vamos a usar es __Authentication__ y __Firestone Database__
18. Instalar la __librería de Firebase__
> yarn add firebase

19. Agregar la configuración para conectar
20. importar:

```jsx
import {initializeApp} from 'firebase/app'
import {
  getAuth, signInWithRedirect, signInWithPopup, GoogleAuthProvider   
}

```
21. Agregar el form y darle estilo

```scss
$sub-color: grey;
$main-color: black;

@mixin shrinkLabel {
  top: -14px;
  font-size: 12px;
  color: $main-color;
}

.group {
  position: relative;
  margin: 45px 0;

  .form-input {
    background: none;
    background-color: white;
    color: $sub-color;
    font-size: 18px;
    padding: 10px 10px 10px 5px;
    display: block;
    width: 100%;
    border: none;
    border-radius: 0;
    border-bottom: 1px solid $sub-color;
    margin: 25px 0;

    &:focus {
      outline: none;
    }

    &:focus ~ .form-input-label {
      @include shrinkLabel();
    }
  }

  input[type='password'] {
    letter-spacing: 0.3em;
  }

  .form-input-label {
    color: $sub-color;
    font-size: 16px;
    font-weight: normal;
    position: absolute;
    pointer-events: none;
    left: 5px;
    top: 10px;
    transition: 300ms ease all;

    &.shrink {
      @include shrinkLabel();
    }
  }
}
```
22. Utilizar __createContext__
23. 






































