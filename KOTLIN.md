# KOTLIN

## STARTING

```kotlin
fun main(){
  print("Hello world !")
}
```
* We do not need classes
* We do not use ";" at the end


## VARIABLES, VALUES AND CONSTANTS

__variables__ <br/>
>var name = "Fernando"

__values__ <br/>
>val name = "Fernando"

__constants__ <br/>
>const val name = "Fernando"
__constants has to be in an outter__





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

## ANDROID STUDIO

### MAGIC 8 BALL PROJECT

* Use preset images of the same ball
* Messages:
  + IT IS CERTAIN
  + IT IS DECIDEDLY SO
  + WITHOUT A DOUBT
  + YES - DEFINITELY
  + YOU MAY RELY ON IT
  + AS I SEE IT, YES
  + MOST LIKELY
  + OUTLOOK GOOD
  + YES
  + SIGNS POINT TO YES
  | REPLY HAZY, TRY AGAIN  
  | ASK AGAIN LATER
  | BETTER NOT TELL YOU NOW
  | CANNOT PREDICT NOW
  | CONCENTRATE AND ASK AGAIN
  - DON'T COUNT ON IT
  - MY REPLY IS NO
  - MY SOURCES SAY NO
  - OUTLOOK NOT SO GOOD
  - VERY DOUBTFUL

__starting the project__ <br/>

* Add ImageView
* Select Empty Magic Ball
* Add a button below and adjust margins
* Go to right - up and change to TEXT Mode
* Change text to button
* Inside, at the bottom of Override fun __onCreate__ add:
>val askMeButton: Button = findViewById(R.id.button)
>askMeButton.setOnClickListener{shakeBall()}
* Implement the function:

```kotlin
private fun shakeBall(){
  val ballImageView: ImageView = findViewById(R.id.imageView)
  val randomChoice = Random().nextInt(20)+1

  val imageResource = when(randomChoice){
    1 -> R.drawable.magic_8_ball_1
    2 -> R.drawable.magic_8_ball_2
    3 -> R.drawable.magic_8_ball_3
    4 -> R.drawable.magic_8_ball_4
    else -> R.drawable.magic_8_ball_20
  } 
}
```
* Check documentation for Android create Launcher Icon






