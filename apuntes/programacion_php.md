# PHP

> We have to enclose our code in:

```php
<?php 
// Our code! - This is a comment
?>
```

* Run lampp in Linux

```bash
./xampp start
```

* Stop service lampp in Linux

```bash
./xampp stop
```


### PHP Info

```php
<?php
phpinfo();
?>
```

## CONSTANTS


* __define__ 

```php
<?php 
define('DOMAIN', 'www.google.com');
?>
```

* __defined__

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


* __strlen__ 

> Length of a string 

```php
strlen($my_string);
```

* __str_word_count__ 

How many words has the string <br/>

```php
str_word_count($my_string);
```


* __substr__ 

> Substract a part of a string

```php
substr($my_string, 0, 5);
```

> Where __0__ is position and __5__ is the number of characters. 

<br/>


* __rand()__ 

```php
rand(1,6)
```


