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

> Es mejor para COLECCIONES

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
numbers.forEach { number ->
    println(number)
}
```
> Podemos auxiliarnos del iterador de lambda "it"

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
numbers.forEach { println(it)}
```

## Clases


### Clases de Datos

> Son clases especiales, ideales para almacenar datos. Generan métodos como:

* toString()
* equals()
* hashCode()
* copy()


## FUNCIONES


### Funciones

```kotlin
fun sumar(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val resultado = sumar(5, 3)
    println("La suma de 5 y 3 es: $resultado")
}

```


### Funciones con Argumentos Nombrados

```kotlin
fun greet(name: String, greeting: String = "Hello") {
    println("$greeting, $name!")
}

fun main() {
    greet(name = "Juan", greeting = "Hola")
    greet(greeting = "Hi", name = "Ana")
    greet(name = "Carlos")
}
```


### Funciones Infix

> Son funciones que se utilizan sin el operador "."
> La funcion "to" ya viene incluida en Kotlin

```kotlin
fun main() {
    val pair = "key" to "value"
    println(pair) // Output: (key, value)
}
```

```kotlin
data class Vector(val x: Int, val y: Int)

infix fun Vector.add(other: Vector): Vector {
    return Vector(this.x + other.x, this.y + other.y)
}

fun main() {
    val vector1 = Vector(1, 2)
    val vector2 = Vector(3, 4)
    val result = vector1 add vector2
    println(result) // Output: Vector(x=4, y=6)
}
```

### Funciones LAMBDA

> Son una función SIMPLIFICADA o Bloque de código
> Se construyen solo con llaves
> La flecha divide los parámetros del cuerpo

```kotlin
val suma = { x:Int, y:Int -> x + y }

print(suma(1,2))
```

> Declarar una variable de tipo lambda

```kotlin
val addToFive: (Int)->Int = {
  it + 5
}

println(addToFive(5))
```

### Función de ORDEN SUPERIOR

> Reciben como parámetro OTRA función


## COLECCIONES

> Las siguientes colecciones son INMUTABLES
> Les agregamos mutable para hacerlas MUTABLES

### List

> Ya las habíamos visto anteriormente con "forEach"

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
numbers.forEach { println(it)}
```

### Set

> Guarda solo valores UNICOS
> Es decir, desecha los repetidos

```kotlin
val numbers = setOf(1, 2, 2, 3, 1)
numbers.forEach { println(it) }
```

### Map

> Guarda clave - valor

```kotlin
val listado = mapOf(
    1 to "Rock", 
    2 to "Jazz",
    3 to "Electronic"
)
    
listado.forEach { 
  val llave = it.key
  val valor = it.value
  println("$llave. $valor")
}
```

### Predicados Funcionales

* filter / filterNot / partition

```kotlin
val edades = listOf(22,34,17,14,15,48,45,19)
val mayores = edades.filter{it >= 18}
val menores = edades.filterNot{it >= 18}

println(mayores.joinToString())
println(menores.joinToString())

val usa = edades.partition{it >= 21}
val mayoresUSA = usa.first
val menoresUSA = usa.second

println(mayoresUSA.joinToString())
println(menoresUSA.joinToString())
```

## OPERADOR ELVIS

```kotlin
return ?:0
```












