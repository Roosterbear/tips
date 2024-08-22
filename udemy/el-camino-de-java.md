# EL CAMINO DE JAVA

## ARREGLOS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

Podemos declarar arrays de las siguientes formas: <br/>

```java
double[] array;
int arr[] = {1,2,3};
int arr[] = new int[5];
```

* Ordenar un arreglo

```java
Array.sort(miArreglo);
```


## CICLOS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@


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


## PROGRAMACION ORIENTADA A OBJETOS @@@@@@@@@@@@@

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



## EXCEPCIONES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

> Todas las excepciones son objetos de la clase Throwable