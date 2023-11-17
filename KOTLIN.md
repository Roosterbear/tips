# KOTLIN

## STARTING

```kotlin
fun main(){
  print("Hello world !")
}
```
* We do not need classes
* We do not use ";" at the end


## VARIABLES AND CONSTANTS

__variables__ <br/>
>var name = "Fernando"

__constants__ <br/>
>val name = "Fernando"

* Kotlin is __NOT__ dinamically typed
* We do not __need__ to _declare_ a type
* If we use a type, __IT CAN NOT BE CHANGED__
* If you want a __explicit__ type:

>var radius: Int = 7
>val PI: Double = 3.1416
>var name: String = "Fernando"
>var isAdult: Boolean
>var isMan = true

## ARRAYS AND LISTS

* Arrays
>var myArray = arrayOf(true,2,"tres")
>var myNames = arrayOf<String>("Jacinto", "Jeremías", "Panchito")

* Lists _(are inmmutables)_
>var myList = listOf(1,2,"tres",3.5)
>var myNames = listOf<String>("Jacinto", "Jeremias", "Panchito")

* Mutable Lists
>var myMutable = mutableList<Double>(1.1, 2.2)
>myMutable.add(3.3)


## MAPS AND SETS

* Maps

```kotlin
fun main(){
  val map = mutableMapOf("a" to 1, "b" to 2)
  map["c"] = 3
  println(map["a"])
  for((key, value) in map){
    println(key)
    println(value)
  }
}
```

* Sets
__We will get UNIQUE values__ <br/>

```kotlin
fun main(){
  val text = "ANITA LAVA LA TINA"
  var letterSet = mutableSetOf<Char>()
  for(letter in text){
    letterSet.add(letter)
  }
  println(letterSet.size)
}
```





