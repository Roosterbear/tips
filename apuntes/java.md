# EL CAMINO DE JAVA

## CONCEPTOS BASICOS @@@@@@@@@@@@@@@@@@@@@@@


### Estructura

```java
public class HolaMundo{
  public static void main(String[] args){
    System.out.println("Hola Mundo");
  }
}
```

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
> Es la combinacion de un registro
> con funciones para manipular sus datos
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


> EL COMPILADOR AGREGA POR DEFAULT:

* UN CONSTRUCTOR 
* UNA LLAMADA A super()

> LOS CONSTRUCTORES SE LLAMAN IGUAL QUE LA CLASE
> LOS CONSTRUCTORES NO LLEVAN TIPO DE RETORNO
> LOS CONSTRUCTORES NO LLEVAN ARGUMENTOS
> LOS CONSTRUCTORES SE LLAMAN SOLO AL CREAR UNA INSTANCIA


### Accesors / Mutators

> Debido a que los datos de una instancia es por lo general
> declarados con visibilidad __privada__
> una clase provee servicios para acceder y modificar valores.
<br/>

> Un método como __getData__ se le llama __ACCESOR__ porque 
> provee acceso de "solo-lectura" a un valor particular.
<br/>

> Igualmente, un método como __setData__ se llama __MUTATOR__
> porque cambia un valor en particular.
<br/>


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
> La forma de crear un wrapper de manera explicita es con __valueOf__

```java
Integer i = Integer.valueOf(123456);
```

> O más comunmente, de manera implícita (directa)

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

## DATE 

> Tenemos que importar __java.util.Date__

```java
SimpleDateFormat df1 = new SimpleDateFormat("dd MMMM, yyyy");
SimpleDateFormat df2 = new SimpleDateFormat("dd-MM-yyyy");
SimpleDateFormat df3 = new SimpleDateFormat("dd/MMM/yyyy");

String fechaStr = df.format(fecha);
```


## ENUM

> Son una alternativa al uso de CONSTANTES
> ya que describen un conjunto de elementos
> que pueden ser asignados o comparados.

```java
public enum PowerStatus {OFFLINE, ONLINE};
```

> Lo podemos usar de la siguiente manera:

```java
PowerStatus pow = PowerStatus.ONLINE;
if(pow = PowerStatus.ONLINE){
  System.out.println("Encendido");
}
```


## String Builder

```java
StringBuilder sb = new StringBuilder();
sb.append("Hola Mundo");
```

## StringTokenizer

```java
import java.util.StringTokenizer;
public class StringTokenizerDemo{
  public static void main(String[] args){
    String str = "1,2,3,4,5,6,7,8,9";
    StringTokenizer st = new StringTokenizer(str, ", ");
    while(st.hasMoreTokens()){
      String s = st.nextToken();
      System.out.println(s);
    }
  }

}

```

## Interface

> Es un conjunto de declaraciones de métodos
> Es como establecer un CONTRATO, donde una clase
> declara que implementa todos los métodos
> establecidos en esa interface


## Anotaciones

> Es la manera de tener una REFERENCIA dentro de la clase
> y mostrar información UTIL


## EXCEPCIONES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> Todas las excepciones son objetos de la clase Throwable