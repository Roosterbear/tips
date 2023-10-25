# PHP

We have to enclose our code in __<?php__ and __?>__ tags.

### Run lampp in Linux

>./xampp start

Stop service lampp in Linux: <br/>

>./xampp stop


### PHP Info

```php
<?php
phpinfo();
?>
```

## CONSTANTS

__define__ <br/>

```php
<?php 
define('DOMAIN', 'www.google.com');
?>
```

__defined__ <br/>

```php
<?php 
defined('EXEC') or die;
?>
```
* Checks if is _EXEC_ defined (with define or const)

### var_dump()

>var_dump($value);

Shows the type and value of a variable. <br/>

### print_r

```php
echo "<pre>".print_r($this->user, true)."</pre";
```

### htmlspecialchars($id)

* Escapes HTML special characters to avoid hacking the site. <br/>
<br/>



### HEADER

Sends us to other site: <br/>

>header("Location: index.php");



## STRINGS

__strlen__ <br/>

Length of a string <br/>

>strlen($my_string);

__str_word_count__ <br/>

How many words has the string <br/>

>str_word_count($my_string);


__substr__ <br/>

Substract a part of a string <br/>

>substr($my_string, 0, 5);

Where __0__ is position and __5__ is the number of characters. <br/>

<br/>

__implode / explode__ <br/>

__rand()__ <br/>

>rand(1,6)

__mt_rand()__ <br/>

__shuffle()__ <br/>

### __toString()


### SESSION

### REQUEST

__get__ <br/>

__post__ <br/>


## isset()

__md5()__ <br/>

__include / require__ <br/>

__is_numeric()__ <br/>

__slug_url()__ <br/>

__redirect()__ <br/>

__sw_count()__ <br/>

__empty()__ <br/>

__file_exists()__ <br/>

__readdir()__ <br/>

__substr_count()__ <br/>

__ob_start()__ <br/>

__get_template_part()__ <br/>

__password_hash__ <br/>

__http_response_code()__ <br/>



## INVOKE


## GENERATORS




# MVC

We need to have the next folders structure: <br/>

>app

__app/libraries/__ core.php <br/>
__app/libraries/__ database.php <br/>
__app/libraries/__ controller.php <br/>
__app/helpers__ <br/>
__app/config__ <br/>
__app/controllers__ <br/>
__app/models__ <br/>
__app/views__ <br/>
__app/__ bootstrap.php <br/>
__app/__ .htaccess <br/>

>public

__public/css/__ style.css <br/>
__public/js/__ main.css <br/>
__public/img__ <br/>
__public/__ index.php <br/>





