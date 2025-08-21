<h1 style="color:#e63946">JAVA</h1>

- [BASICO](#basico)
  - [Hola Mundo](#hola-mundo)
  - [FOR Mejorado](#for-mejorado)
  - [Comprobación de Precisión](#comprobación-de-precisión)
  - [Scanner \[Días del año\]](#scanner-días-del-año)
  - [Cadenas](#cadenas)
- [PROGRAMACIÓN ORIENTADA A OBJETOS](#programación-orientada-a-objetos)
  - [Clases](#clases)
  - [Clases Abstractas](#clases-abstractas)
  - [Interfaces](#interfaces)
  - [Sets](#sets)
  - [Java Beans](#java-beans)
  - [Función Lambda](#función-lambda)
  - [Método de Referencia](#método-de-referencia)
- [BASES DE DATOS](#bases-de-datos)


# BASICO

## Hola Mundo

```java
public class Prueba{
  public static void main(String[] args){
    System.out.println("Hola Mundo");
  }
}
```

## FOR Mejorado

```java
public class Prueba{
  public static void main(String[] args){
    String[] nombres = {"Jeremias", "Panchito"};
    for(String n:nombres){
      System.out.println(n);
    }
  }
}
```

## Comprobación de Precisión

```java
public class Prueba{
  public static void main(String[] args){
    Long numerote = Long.MAX_VALUE;
    Double numerotote = Double.MAX_VALUE;

    System.out.println("MAX Long: "+numerote);
    numerote = numerote-1;
    System.out.println("Menos uno = "+numerote);

    System.out.println("MAX Double: "+numerotote);
    numerotote = numerotote-1;
    System.out.println("Menos uno = "+numerotote);
  }
}
```

## Scanner [Días del año]

```java
import java.util.Scanner;

public class Prueba{
  public static void main(String[] args){
    Scanner consola = new Scanner(System.in);
    int month = 0;
    int year = 0;

    while(true){
      System.out.print("Dame un número del mes [1..12]: ");
      var monthInput = consola.nextLine();
      month = Integer.parseInt(monthInput);
      if (month>0 && month<13) break;
    }

    System.out.print("Dame el año: ");
    var yearInput = consola.nextLine();
    year = Integer.parseInt(yearInput);

    System.out.println("-------------------------");
    System.out.println("Ese mes tiene "+daysInMonth(month, year)+" días");
  }

  public static int daysInMonth(int month, int year){
    int[] days = {0,31,28,31,30,31,30,31,31,30,31,30,31};

    // Si es Bisiesto
    if(((year%4)==0)&&(((year%100)!=0)||((year%400)==0)))
      days[2]++;

    return days[month];
  }
}
```
## Cadenas

```java
public class Prueba{
  public static void main(String[] args){
    String a = "a";
    String b = "b";
    String c = a;
  
    StringBuilder sb = new StringBuilder(a);
    long inicio = System.currentTimeMillis();
    for (int i = 0; i < 50000; i++){
      //c = c.concat(a).concat(b).concat("\n");
      //c += a+b+("\n");
      //sb.append(a).append(b).append("\n");
    }

    long fin = System.currentTimeMillis();
    System.out.println(fin-inicio);
    
  }
}
```

# PROGRAMACIÓN ORIENTADA A OBJETOS

## Clases

```java
public class Prueba{
  public static void main(String[] args){
    Persona juanito = new Persona();
    Persona pepito = new Persona();
    juanito.nombre = "Juanito";
    pepito.nombre = "Pepito";
    juanito.juega(pepito);
  }
}

class Persona{
  String nombre;
  void juega(Persona p){
    System.out.println(nombre+" juega con "+p.nombre);
  }
}
```

## Clases Abstractas

- [x] Se usa para abstraer CARACTERÍSTICAS en __comun__

```java
public class Prueba{
  public static void main(String[] args){
    FiguraGeometrica fg = new Rectangulo();
    fg.dibujar();
  }
}

// No se pueden crear Objetos
// Se debe HEREDAR
abstract class FiguraGeometrica{
  public abstract void dibujar();
}

class Rectangulo extends FiguraGeometrica{
  public void dibujar(){
    System.out.println("Dibujando un Rectángulo");
  }
}
```

## Interfaces

- [x] Es un contrato que implementa COMPORTAMIENTOS __reutilizables__

```java
public interface Traductor{
  //
  void traducir();

  default void iniciar(){
    System.out.println("Iniciando traductor...");
  }
}

class Ingles implements Traductor{
  @Override
  public void traducir(){
    System.out.println("Traduciendo a ingles");
  }
}

class Prueba{
  public static void main(String[] args){
    // Clase ingles del tipo Interfaz "Traductor"
    Traductor ingles = new Ingles();
    ingles.traducir();
  }
}
```
## Sets

- [x] Coleccion que no permite elementos repetidos

```java
import java.util.TreeSet;
import java.util.Set;

public class Sets{
  public static void main(String[] args){
    Set<String> conjunto = new TreeSet<>();
    conjunto.add("Luis");
    conjunto.add("Luis"); // Ya no mostrará este elemento
    conjunto.add("Fernando");
    conjunto.add("Jeremias");

    System.out.println("Elementos del Set");
    conjunto.forEach(System.out::println);
  }
}
```

## Java Beans

- [x] Es una clase de JAVA que debe cumplir ciertas caracteristicas:

* Al menos un CONSTRUCTOR __vacío__
* Minimo un ATRIBUTO PRIVADO con su __get__ y su __set__
* Implementar la INTERFACE __Serializable__

```java
import java.io.Serializable;

public class Prueba{
  public static void main(String[] args){
    var persona = new Persona();
    persona.setNombre("Fernando");
    persona.setApellido("Roosterbear");
    System.out.println(persona);
  }
}

class Persona implements Serializable{
  private String nombre;
  private String apellido;

  public Persona(){}

  public String getNombre(){
    return nombre;
  }

  public void setNombre(String nombre){
    this.nombre = nombre;
  }

  public String getApellido(){
    return apellido;
  }

  public void setApellido(String apellido){
    this.nombre = apellido;
  }
}

```
## Función Lambda

- [x] Función __anónima__ de código COMPACTO

```java
import java.util.ArrayList;
import java.util.List;

public class Prueba{
  public static void main(String[] args){

    List<String> miLista = new ArrayList<>();
    miLista.add("Lunes");
    miLista.add("Martes");
    miLista.add("Miercoles");
    miLista.add("Jueves");
    miLista.add("Viernes");

    miLista.forEach(elemento->{
      System.out.prinln("Elemento: "+elemento);
    });
  }
}
```

## Método de Referencia

- [x] Toma de referencia el valor y lo imprime

```java
import java.util.ArrayList;
import java.util.List;

public class Prueba{
  public static void main(String[] args){

    List<String> nombres = Arrays.asList("Jacinto","Jeremias","Panchito");
    miLista.forEach(System.out::println);

  }
}
```

# BASES DE DATOS

- [x] Crear proyecto Java - Maven
- [x] Agregar Dependencias en el __pom.xml__

* Al agregar la etiqueta __dependency__ se agregaran __groupId__ y __artifactId__

```xml
<dependencies>
  <dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>8.3.0</version>
  </dependency>
</dependencies>
```

- [x] Actualizar Maven desde el IDE
- [x] Agregar paquete y Clase de Conexión

```java
import java.sql.Connection;

public class Conexion{
  pulic static Connection getConexion(){
    Connection conexion = null;
    var baseDatos = "mi_bd";
    var url = "jdbc:mysql://localhost:3306/"+baseDatos;
    var usuario = "root";
    var password = "admin";
    try{
      Class.forName("com.mysql.cj.jdbc.Driver");
      conexion = DriverManager.getConnection(url, usuario, password);
    }catch(Exception e){
      System.out.println("Error al conectar BD: "+e.getMessage());
    }

    return conexion;
  }

  public static void main(String[] args){
    var conexion = conexion.getConexion();
    if(conexion != null)
      System.out.println("READY: "+conexion);
    else
      System.out.println("ERROR: No se pudo conectar la BD");
  }

}
```
- [x] Si no reconoce la clase Connection: __Invalidar Caché__
- [x] Crear el __DOMINIO__ de nuestra aplicación
<br/>

- [x] Debemos mapear los campos de la __BD__ con variables en Java

```java
public class Cliente{
  private int id;
  private String nombre;
  private String apellido;
  private int membresia;

  // Constructor si no le pasamos parámetros
  public Cliente(){}

  // Constructor si no le pasamos el Id
  public Cliente(int id){
    this.id = id;
  }

  // Constructor si le pasamos algunos parámetros
  public Cliente(String nombre, String apellido, int membresia){
    this.nombre = nombre;
    this.apellido = apellido;
    this.membresia = membresia;
  }

  // Constructor si le pasamos TODOS los parámetros
  public Cliente(){
    this(nombre, apellido, membresia);
    this.id = id;
  }

  //
  // GENERAR LOS Getters, Setters, ToString, Equals y Hascode
  //
}
```
