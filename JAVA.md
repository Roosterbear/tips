# JAVA

## JDK - Java Development Kit

Let instalation in root folder <br/>


## CLASS

A __template__ that describes the kinds of state and behavior that objects of its type support. <br/>


### Object

At runtime, when the Java Virtual Machine (JVM) encounters the _new_ keyword, it will use the appropiate __class__ to make an object which is an instance of that class. That object will have its own __state__, and __access__ to all the behaviors defined by his class. <br/>


### State (_instance variables_)

Each __object__ (_instance of a class_) will have its own unique set of instance variables as defined in the class. Collectively, the values assigned to an object's instance variables make up the object's state. <br/>


### Behavior (_methods_)

When a programmer creates a class, he creates methods for that class. Methods are where the class logic is stored. Methods are where the real work gets done. They are where algorithms get executed, and data gets manipulated.


### JShell

* __jshell__ to open the java shell
* __/exit__ to exit
* __/edit__ to open editor
* __alt+Enter__ to write a new line without executing
* __/var__ list all created variables
* __/list__ list what was executed


__modules__ <br/>

Since version 9 there are modules, where we can find our packages. <br/>

__compile in different path__ <br/>

>javac -d c:\javaprojects\build com\roosterbear\MyProject.java

__exec from different path__ <br/>

>java -cp c:\javaproject\build com.roosterbear.MyProject

__difference between Long and Double__ <br/>

They are the largest places where we can store a value. <br/>

>Long numerote = Long.MAX_VALUE;
>Double numerotote = Double.MAX_VALUE;

Now... <br/>
> numerote = numerote -1;
> numerotote = numerotote -1;

Check the difference!!, Double doesn't have __precision__ !! <br/>


__Get the current TIME__ <br/>

>System.currentTimeMillis();

__Get info from user__ <br/>

>import java.util.Scanner;
>Scanner console = new Scanner(System.in);
>System.out.print("Gimme data: ");
>var data = console.nextLine();

__tags__

Used to know which iteration to break:

```java
outer: for(int j = 0; j<=10; j++){
  inner: for(int i = 0; i<=10; i++){
    break outer;
  } 
}
```

## ARRAYS

Defining: <br/>

__RECOMMENDED__ <br/>
>double[] = array;

_Legal but less readable_ <br/>
>double array[];

It's __NOT LEGAL__ to include the size of the array in your declaration. <br/>
The __JVM__ doesn't  allocate space until you actually instantiate the array __OBJECT__ <br/>


Both are right!! <br/>

```java
int data[] = {
  1,
  2,
  3,
}
```

Check the last __comma__ it is right that way! <br/>


## ITERATIONS

__enhanced FOR__ <br/>

```java
for(double d : arr){
  sum+=d;
}
```

__weird FOR__ <br/>

```java
int i = 0;
for(;i<5;){
  i++;
  System.out.println(i);
}
```

## CONSTANTS

>static final int MAX_SIZE = 1024;
>static final boolean DEBUG = true;

### RANDOM

```java
int dice = (int)(Math.random()*6+1);
```

* Math.random gives decimals, we need to convert to __int__
* If we multiply __by 6__ we get the numbers to consider
* Math.random starts by 0, we need to __add 1__ to avoid this


## STRINGS

_STRINGS IN JAVA ARE IMMUTABLE_ <br/>

### StringBuilder

StringBuilder sb = new StringBuilder();
sb.append("Hola Mundo");




## CLASSES




### Instanceof

In the code:

```java
Person worker = new Employee();
```
We have the type _Person_ called worker, and aims to the Employee __memory reference__. <br/>






## LISTS

>lista.forEach(System.out::println)







## MAVEN

* It is a tool to manage projects
* Its main function is to help developers to build, manage and organize Software Projects
* Uses a configuration file called __"pom.xml"__ (_Project Object Model_)