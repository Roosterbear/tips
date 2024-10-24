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

### Inmutabilidad

> Kotlin trabaja con el paradigma FUNCIONAL
> es decir, prefiere que las cosas NO CAMBIEN


### Variables

> Hay variables reutilizables y NO reutilizables

* __REUTILIZABLES__

```kotlin
var nombre = "Luis"
```

* __INMUTABLE__

```kotlin
val numero = 10 
```

* Especificar el tipo

```kotlin
val age: Byte = 20
```

> PODEMOS USAR LA TECNICA __SEO__ PARA CREAR NOMBRES DE VARIABLES
> ES DECIR, USAR LA FORMA MAS OBVIA DE BUSCAR ALGO


### Strings

> Para escribir variables dentro de cadenas usamos:

```kotlin
val texto = "Total: $variable"
```


### Métodos de conversión
> Los tipos de datos cuentan con FUNCIONES que podemos usar


## Arrays

> Siempre guardan sus valores de forma __CONSECUTIVA__ en memoria
> Es como cuando vamos al cine y queremos nuestros asientos juntos

```kotlin
val myArray = arrayOf(1,"hola",true)
val emptyArray = emptyArray<Int>()
```

> Para ver el tamaño de un array:

```kotlin
val greetings = arrayOf("Hola", "como", "estas")
greeting.size
```

### Arrays tipados (PRIMITIVOS)

```kotlin
val numeros = IntArray(size)
```

### Arrays tipados (DE OBJETOS)

```kotlin
val numeros: Array<Int>
```

### Ejemplo de ARRAYS

```kotlin
val saludos = arrayOf("Hola","Como estas","Que onda","Quiubo","Que tal")    
val intros = arrayOf("mi nombre es","me llamo","yo soy","dime")
val nombres = arrayOf("Roosterbear","Fernando","Luis")

val saludo = saludos[(Math.random()*saludos.size).toInt()]
val intro = intros[(Math.random()*intros.size).toInt()]
val nombre = nombres[(Math.random()*nombres.size).toInt()]

println("$saludo $intro $nombre")
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

```kotlin
for(i in 'c'.downTo('a')){
  println(i)
}
```


```kotlin
val saludos = arrayOf("Hola","Hi","Que tal","Quiubo", "Que onda","Que pasa")
for(i in saludos.indices){
    println(saludos[i])
}
```

### Foreach

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
numbers.forEach { number ->
    println(number)
}
```



## FUNCIONES


### Funciones

```
```


### Funciones con Argumentos Nombrados

```
```


### Funciones Infix

```
```
























