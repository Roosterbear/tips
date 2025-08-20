<h1 style="color:#e63946">JAVA</h1>

- [BASICO](#basico)
  - [Hola Mundo](#hola-mundo)
  - [FOR Mejorado](#for-mejorado)
  - [Comprobación de Precisión](#comprobación-de-precisión)
  - [Scanner \[Días del año\]](#scanner-días-del-año)
- [PROGRAMACIÓN ORIENTADA A OBJETOS](#programación-orientada-a-objetos)
- [Clases Abstractas](#clases-abstractas)
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

# PROGRAMACIÓN ORIENTADA A OBJETOS

# Clases Abstractas

```java
public class Prueba{
  public static void main(String[] args){
    FiguraGeometrica fg = new Rectangulo();
    fg.dibujar();
  }
}

abstract class FiguraGeometrica{
  public abstract void dibujar();
}

class Rectangulo extends FiguraGeometrica{
  public void dibujar(){
    System.out.println("Dibujando un Rectángulo");
  }
}
```



```java

```









```java

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









