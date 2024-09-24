# EL CAMINO DE JAVA

## CONCEPTOS BASICOS @@@@@@@@@@@@@@@@@@@@@@@

### Arrays

Podemos declarar arrays de las siguientes formas: <br/>

```java
double[] arr;
int arr[] = {1,2,3};
int arr[] = new int[5];
```

* Ordenar un arreglo

```java
Array.sort(miArreglo);
```

### Ciclo FOR Mejorado

* Normal

```java
for(int n=0;n<arr.length;n++){
  sum += arr[n];
}
```

* Mejorado

```java
for(double d:arr){
  sum += d;
}
```

### While

```java
double sum = 0;
int n = 0;
while(n<arr.length){
  sum = sum+arr[n];
  n++;
}
return sum/arr.length;
```

### Do While

```java
int n = 0;
do{
  n++;
}while(n<10);
```

* Break
> Termina el ciclo 

* Continue
> Brinca al inicio del ciclo


## PROGRAMACION ORIENTADA A OBJETOS @@@@@@@@

> Es un metodo de programacion que IMITA la manera en que
> hacemos las cosas.

Existen 3 propiedades principales: <br/>

### Encapsulamiento
> Es la combinacionde un registro
> con funciones paramanipular sus datos
> con lo que forma un nuevo tipo de dato: EL OBJETO

### Herencia
> Se refiere a definir un objeto y entonces usarlo para
> construir una jerarquia de objetos descendientes
> donde cada descendiente hereda el acceso al codigo y datos
> de su antecesor

### Polimorfismo
> Es darle un nombre a la ACCION que se comparte
> de arriba a abajo en la jerarquia de objetos,
> donde cada objeto en la misma jerarquia
> implementa la accion de una forma unica para si mismo
> Es la capacidad de las clases de definir su propio COMPORTAMIENTO
> ademas de heredar la funcionalidad de su antecesor.


### Clases

> Son moldes para crear objetos


### Sobrecarga de metodos

> Definir varias funciones con el mismo nombre
> siempre y cuando el tipo de datos sea DIFERENTE


### Niveles de acceso

|  | Clase | Package | Subclase | Mundo | Proteccion |
| :---: | :---: | :-----: | :-----: | :-----: | :-----: |
| Public | si | si | si | si | Sin proteccion |
| Protected | si | si | si | NO | Protegido contra el Mundo |
| Private | si | NO | NO | NO | Acceso solo la __CLASE__ |
| Ninguno | si | si | NO | NO | Acceso _private-package_ |


### Herencia

```java
public class Point{
  public int x, y;
}

public class Circle extends Point{
  public int radius;
}

public class Rectangle extends Point{
  public int width, height;
}

Point p = new Point(); // CORRECTO: Es del mismo tipo
Point c = new Circle(); // CORRECTO: La variable es mas general que el tipo
Point r = new Rectangle(); // CORRECTO: La variable es mas grande que el contenido

Circle c = new Point(); //ERROR: El contenido es mas general que la variable
Rectangle r = new Point(); //ERROR: La variable es mas especifica que el contenido
```

## WRAPPERS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> Tipos de datos de referencia o clase basados en __PRIMITIVOS__
> Dan mayor funcionallidad para operaciones de comprobaciones y conversiones

| Primitivo | Clase Equivalente | 
| :---: | :---: | 
| byte | Byte | 
| short | Short | 
| int | Integer | 
| long | Long | 
| float | Float | 
| double | Double | 
| char | Character | 
| boolean | Boolean | 

__BOXING__

> Ya no se utiliza el constructor _new_ para crear __wrappers__
> La forma de crear un wrapper de manera explicita con __valueOf__

```java
Integer i = Integer.valueOf(123456);
```

> Aunque podemos hacerlo de manera implícita

```java
Integer i = 123456;
```

__UNBOXING__

> De igual manera podemos convertir de manera implícita y explícita:

```java
Integer intObjeto = 123456;

int num1 = intObjeto.intValue();
int num2 = intObjeto;

```

## EXCEPCIONES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> Todas las excepciones son objetos de la clase Throwable