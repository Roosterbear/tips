<h1 style="color:#f4a261">CURSO COMPLETO PHP</h1>

- [INTRODUCCIÓN](#introducción)
- [GENERADORES](#generadores)

# INTRODUCCIÓN

- [x] Instalar PHP en WSL

```sudo apt update && sudo apt upgrade -y``` <br/>
```sudo apt install php php-mysql php-curl php-gd php-mbstring php-xml php-zip -y``` <br/>
```sudo apt install apache2 libapache2-mod-php -y  # Ubuntu/Debian``` <br/>
```sudo service apache2 start``` <br/>

- [x] Trabajar en ```/var/www/html/```
- [x] Dar permisos: <br/> 
  ```sudo chown -R $USER:$USER /var/www/html/``` y <br/>
  ```sudo chmod -R 755 /var/www/html/``` <br/>
- [x] Para direccionar Apache, crear archivo: <br/>
  ```sudo nano /etc/apache2/sites-available/proyecto.conf``` y agregar: <br/>

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
- [x] Habilitar el sitio, deshabilitar default y recargar Apache: <br/>

```sudo a2ensite proyecto.conf``` <br/>
```sudo a2dissite 000-default.conf``` <br/>
```sudo service apache2 reload``` <br/>

- [x] Dar permisos a Apache (usuario __www-data__) sobre nuestra carpeta:

```sudo chown -R $USER:www-data ~/proyectos```
```sudo chmod -R 775 ~/proyectos```

- [x] Crear enlace entre Windows y Linux en WSL:

```sudo ln -s /mnt/c/Users/usuario/Desktop/proyectos /var/www/html/proyectos```


# GENERADORES

- [x] Se utilizan para ahorrar memoria, ya que van pasando los datos mientras se van usando:

```php
function rango($inicio, $fin, $incremento=1){
    for($i=$inicio;$i<=$fin;$i+=$incremento){
        yield $i;
    }
}
```
















