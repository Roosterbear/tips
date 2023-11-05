# WORDPRESS

## LOCAL INSTALLATION

Install: <br/>

>https://localwp.com/

Configuration: <br/>

* CREATE A NEW SITE - Site name: Roosterbear
* Preferred
* Add username, password and email


## CUSTOMIZATION



## PLUGINS

>wp-content - plugins

Add a file with a unique name and the next code: <br/>

```php
<?php
/*
*
* Plugin Name: The Name of Your Plugin
* Plugin URI: www.myweb.com
* Description: This plugin does not do a shit
* Version: 1.0
* Author: R00sterbear
* License: GPL2
*
*
*/
?>
```




## WOOCOMMERCE

__Discounts__ <br/>
In simple products, we have to write the regular Price and Sale price (discounted price).<br/>
We can add date for that sale.<br/>

__Stock__ <br/>
* We have to check "Enable stock". 
* Add Stock quantity
* Add Low stock threshold

__Linked Products__ <br/>
Upsells (Other products to offer when below as "other products")<br/>
Cross-sells (Other products to offer in the shopping car)<br/>

__Advanced__ <br/>
Menu order (Order when the products shows in the Shop page)<br/>
Product short description (The most important information)<br/>

__Grouped products__ <br/>
This is very useful for products with different prices. <br/>
Create a new product with all data, but __NO PRICE__ <br/>
In product data, change to __"Grouped product"__ <br/>
Now we need to create new children products the same way we create a normal __SINGLE__ product. <br/>
Do not add data, only __PRICE__ <br/>
Name them as the characteristic of every child product (16Gb, Extra Large, Core i7, 35inch, Signature) <br/>
We have to select "hidden" in Catalog visibility <br/>
Edit parent product and select __Linked Products__ and write the names of the Children Products to add them <br/>

__External / Affiliate__ <br/>
In product data, change to "External / Affiliate product" <br/>
In product URL add the link.<br/>
In Button text, add any text you want. <br/>
