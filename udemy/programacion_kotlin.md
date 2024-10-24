# KOTLIN

## INTRODUCCION

1. Instalar IntelliJ IDEA Community
2. Crear nuevo proyecto de Kotlin
3. Agregar en __src__ un nuevo archivo __Main.kt__
4. Instalar plugins de __VSCode:__ Kotlin y Kotlin Language

```kotlin
fun main(){
  println("Hola Mundo")
}
```

### Variables

> Hay variables reutilizables y NO reutilizables

* REUTILIZABLES 

```kotlin
var nombre = "Luis"
```

* NO Reutilizables

```kotlin
val numero = 10 
```

* Especificar el tipo

```kotlin
val age: Byte = 20
```

> PODEMOS USAR LA TECNICA SEO PARA CREAR NOMBRES DE VARIABLES
> ES DECIR, USAR LA FORMA MAS OBVIA DE BUSCAR ALGO


### Strings

> Para escribir variables dentro de cadenas usamos:

```kotlin
val texto = "Total: $variable"
```


### Métodos de conversión

> Los tipos de datos cuentan con FUNCIONES que podemos usar


### Arrays

> Siempre guardan sus valores de forma consecutiva en memoria

```kotlin
val myArray = arrayOf(1,"hola",true)
val emptyArray = emptyArray<Int>()
val numeros = IntArray(size)
```


> Para ver el tamaño de un array:

```kotlin
val greetings = arrayOf("Hola", "como", "estas")
greeting.size
```


## ESTRUCTURAS DE CONTROL


### When

* Con opciones Booleanas

```kotlin
when (loggedIn){
   true -> println("Logueado")
   false -> println("NO Logueado")
}
```

* Con varios valores como If

```kotlin
val mensaje = when (loggedIn){
   0 -> println("Logged out")
   1 -> println("Logged in")
   -1 -> println("Down")
   else -> "Not found"
}
```


```kotlin
val total = when(productPrices){
  is DoubleArray ->productPrices.sum().roundToInt().toString()
  is Double ->productPrices.roundToInt().toString()
  else ->productPrices.toString()
}
```

### ForIn

```kotlin
for(i in 0..4){
  println(i)
}
```

























