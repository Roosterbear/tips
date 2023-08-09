# PHP

We have to enclose our code in __<?php__ and __?>__ tags.

__constants__ <br/>

```php
<?php 

define('DOMAIN', 'www.google.com');
?>
```

__magic methods__ <br/>

```php
<?php 

public function __get($property){
  if(property_exists($this, $property)){
    return $this->$property;
  }
}

public function __set($property, $value){
  if(property_exists($this, $property)){
    $this->$property = $value;
  }
  return $this;
}
?>
```