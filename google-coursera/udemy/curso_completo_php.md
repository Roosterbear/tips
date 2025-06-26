<h1 style="color:#f4a261">CURSO COMPLETO PHP</h1>

- [INTRODUCCIÓN](#introducción)
- [GENERADORES](#generadores)

# INTRODUCCIÓN

- [x] Instalar PHP en WSL

```sudo apt update && sudo apt upgrade -y```
```sudo apt install php php-mysql php-curl php-gd php-mbstring php-xml php-zip -y```
```sudo apt install apache2 libapache2-mod-php -y  # Ubuntu/Debian```
```sudo service apache2 start```

- [x] Trabajar en ```/var/www/html/```
- [x] Dar permisos: ```sudo chown -R $USER:$USER /var/www/html/``` y ```sudo chmod -R 755 /var/www/html/```
- [x] Para direccionar Apache, crear archivo: ```sudo nano /etc/apache2/sites-available/proyecto.conf``` y agregar:

```xml
<VirtualHost *:80>
    ServerName localhost
    DocumentRoot /home/usuario/proyectos
    <Directory /home/usuario/proyectos>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
- [x] Habilitar el sitio, deshabilitar default y recargar Apache:

```sudo a2ensite proyecto.conf```
```sudo a2dissite 000-default.conf```
```sudo service apache2 reload```

- [x] Dar permisos a Apache (usuario __www-data__) sobre nuestra carpeta:

```sudo chown -R $USER:www-data ~/proyectos```
```sudo chmod -R 775 ~/proyectos```




# GENERADORES

```php
function rango($inicio, $fin, $incremento=1){
    for($i=$inicio;$i<=$fin;$i+=$incremento){
        yield $i;
    }
}
```

















