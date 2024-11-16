# COMPLETE REACT DEVELOPER

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
23. Agregar productos:

```json
[
  {
    "id": 1,
    "name": "Brown Brim",
    "imageUrl": "https://i.ibb.co/ZYW3VTp/brown-brim.png",
    "price": 25
  },
  {
    "id": 2,
    "name": "Blue Beanie",
    "imageUrl": "https://i.ibb.co/ypkgK0X/blue-beanie.png",
    "price": 18
  },
  {
    "id": 3,
    "name": "Brown Cowboy",
    "imageUrl": "https://i.ibb.co/QdJwgmp/brown-cowboy.png",
    "price": 35
  },
  {
    "id": 4,
    "name": "Grey Brim",
    "imageUrl": "https://i.ibb.co/RjBLWxB/grey-brim.png",
    "price": 25
  },
  {
    "id": 5,
    "name": "Green Beanie",
    "imageUrl": "https://i.ibb.co/YTjW3vF/green-beanie.png",
    "price": 18
  },
  {
    "id": 6,
    "name": "Palm Tree Cap",
    "imageUrl": "https://i.ibb.co/rKBDvJX/palm-tree-cap.png",
    "price": 14
  },
  {
    "id": 7,
    "name": "Red Beanie",
    "imageUrl": "https://i.ibb.co/bLB646Z/red-beanie.png",
    "price": 18
  },
  {
    "id": 8,
    "name": "Wolf Cap",
    "imageUrl": "https://i.ibb.co/1f2nWMM/wolf-cap.png",
    "price": 14
  },
  {
    "id": 9,
    "name": "Blue Snapback",
    "imageUrl": "https://i.ibb.co/X2VJP2W/blue-snapback.png",
    "price": 16
  }
]
```


24. Estilo del carrito:

```scss
.cart-icon-container {
  width: 45px;
  height: 45px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  .shopping-icon {
    width: 24px;
    height: 24px;
  }

  .item-count {
    position: absolute;
    font-size: 10px;
    font-weight: bold;
    bottom: 12px;
  }
}
```

25. Estilo del desplegable:

```scss
.cart-dropdown-container {
  position: absolute;
  width: 240px;
  height: 340px;
  display: flex;
  flex-direction: column;
  padding: 20px;
  border: 1px solid black;
  background-color: white;
  top: 90px;
  right: 40px;
  z-index: 5;

  .empty-message {
    font-size: 18px;
    margin: 50px auto;
  }

  .cart-items {
    height: 240px;
    display: flex;
    flex-direction: column;
    overflow: scroll;
  }

  button {
    margin-top: auto;
  }
}
```

26. Estilo del checkout:

```scss
.checkout-container {
  width: 55%;
  min-height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 50px auto 0;

  .checkout-header {
    width: 100%;
    padding: 10px 0;
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid darkgrey;

    .header-block {
      text-transform: capitalize;
      width: 23%;

      &:last-child {
        width: 8%;
      }
    }
  }

  .total {
    margin-top: 30px;
    margin-left: auto;
    font-size: 36px;
  }
}
```

27. Estilo de los items del checkout:

```scss
.checkout-item-container {
  width: 100%;
  display: flex;
  min-height: 100px;
  border-bottom: 1px solid darkgrey;
  padding: 15px 0;
  font-size: 20px;
  align-items: center;

  .image-container {
    width: 23%;
    padding-right: 15px;

    img {
      width: 100%;
      height: 100%;
    }
  }
  .name,
  .quantity,
  .price {
    width: 23%;
  }

  .quantity {
    display: flex;

    .arrow {
      cursor: pointer;
    }

    .value {
      margin: 0 10px;
    }
  }

  .remove-button {
    padding-left: 12px;
    cursor: pointer;
  }
}
```

28. OJO con los redirects en __Netlify__
29. Checar: Reducer y Context
30. Checar Generator Funcions
31. Checar Redux Saga
32. Checar createSlice
33. Checar Apollo y GraphQL
34. Checar React Memo
35. [React Interview Questions:](https://github.com/sudheerj/reactjs-interview-questions?tab=readme-ov-file)
36. Checar Test con: Jest, Enzyme, Mocks and Spies, Snapshot Testing, Connected Components































