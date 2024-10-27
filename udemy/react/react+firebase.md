# REACT + FIREBASE 6.5 Hrs.


## useState

> Importamos el componente __useState__

```jsx
import React, {useState} from 'react'

const Contador = ()=>{
  const [numero, setNumero] = useState(0)
  const Aumentar = ()=>{
    setNumero(numero+1)
  }
  const Reducir = ()=>{
    setNumero(numero-1)
  }

  return(
    <>
      <h2>Elementos: {numero} </h2>
      <button onClick={Aumentar} >Aumentar</button>
      <button onClick={Reducir} >Reducir</button>
    </>
  )
}

export default Contador;
```

## PROYECTO

> yarn add bootstrap firebase react-router-dom

























