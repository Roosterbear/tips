# PHP

## BASICO

> We have to enclose our code in:

```php
<?php 
// Our code! - This is a comment
?>
```

### Run/Stop lampp in Linux

```bash
./xampp start
```

```bash
./xampp stop
```

### Reinstalar phpMyAdmin

```bash
sudo apt-get remove --purge phpmyadmin
sudo apt-get install phpmyadmin
```


### PHP Info

```php
<?php
phpinfo();
?>
```

### define

```php
<?php 
define('DOMAIN', 'www.google.com');
?>
```

### defined

```php
<?php 
defined('EXEC') or die;
?>
```
> Checks if _EXEC_ is defined (with define or const)


### var_dump()

```php
var_dump($value);
```
> Shows the type and value of a variable. 

### print_r

```php
echo "<pre>".print_r($this->user, true)."</pre";
```

```php
htmlspecialchars($id)
```
> Escapes HTML special characters to avoid hacking the site. 

<br/>


### HEADER

> Sends us to other site 

```php
header("Location: index.php");
```


## STRINGS


### strlen

> Length of a string 

```php
strlen($my_string);
```

### str_word_count

How many words has the string <br/>

```php
str_word_count($my_string);
```

### substr

> Substract a part of a string

```php
substr($my_string, 0, 5);
```

> Where __0__ is position and __5__ is the number of characters. 

<br/>


### implode

> Une en una cadena los elementos de un Array

```php
$libros = ['libro1','libro2','libro3'];
$une = implode(" ", $libros);
```

### explode

> Separa una cadena por un caracter como elementos de un Array

```php
$arreglo = explode(" ", $une);
```

### rand()

```php
rand(1,6)
```

### isset()




### empty()

> Revisa si es vacío, null, 0 o false



### is_null()






## AVANZADO

### Archivos


```html
<form action="import" method="post" enctype="multipart/form-data">
  <label for="file"></label>
  <input type="file" name="file">
  <input type="submit" name="submit" value="Import Students">
</form>
```







## CODEIGNITER

### Consultar

> Como consultar una tabla de una BD en Codeigniter

```php
<?php
$this->db->select("*");
$this->db->from("empleados");
$this->db->where("id=1");
$query = $this->db->get();
?>
```

> Saber si existen registros de esa consulta

```php
<?php
if($query->num_rows()>0){
  return $query->result();
}else{
  return NULL;
}
?>
```

> Funcion equivalente a "select * from"

```php
<?php 
$query = $this->db->get('contactos');
$resultado = $query->result();
?>
```

### Insertar

> Dentro de nuestro modelo, crear una función
> creamos un array con los datos de la tabla

```php
<?php 
$array = array(
  "nombre"=>"Luis",
  "apellido"=>"Perea",
  "materia"=>2
);
$this->db->insert("empleados",$array);
?>
```



```
```





```
```




```
```




```
```


