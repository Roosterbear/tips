# I am the 👁️  in the sky 🔓

### ------------------------------------------------------
##  Instalación tryhackme.com
### ------------------------------------------------------

1. Sign in
2. Menu - Access
3. Download VPN File from __Kali Linux__
4. Open folder in a terminal
5. Exec: 

```bash
sudo openvpn File.ovpn
```
6. Refresh OpenVPN Access to se Green Checkmark
7. Now we can go to __Learn__ and access a Room
8. Start a Machine


### ------------------------------------------------------
## Instalación de Burp Suite
### ------------------------------------------------------

* Viene por default en __KALI LINUX__
* Instalar la extensión __Foxy Proxy__
* Ir a __Configuracion__
* Poner un titulo a la conexion
* Agregar direccion de localhost y puerto 8080
* En el navegador escribir __http://burp__
* Bajar certificado con el botón __CA Certificate__
* Abrir configuración de __Firefox__
* Buscar la opcion __"Ver Certificados"__ 
* Oprimir el boton __importar__
* Elegir el archivo bajado anteriormente 
* Checar ambas opciones


### ------------------------------------------------------
## Gathering
### ------------------------------------------------------

https://sitereport.netcraft.com/
https://builtwith.com/
https://crt.sh/


__dirb__

* Trabajar desde consola de Kali Linux

```bash
dirb https://dominio.com
dirb https://dominio.com -X .php,.html
dirb https://dominio.com -o  out.txt
```

__gobuster__

```bash
gobuster dir -u https://dominio.com -w common.txt -o out.txt
```

### ------------------------------------------------------
## SQL Injection
### ------------------------------------------------------

### Para URLs

* Agregar una comilla al final, si manda error: __ES VULNERABLE__

> Ahora agregar: 'OR 1=1


### Para URLs con ORDER BY

1. Agregar 'order by 1--
2. Ir incrementando para ver cuantas columnas tiene la consulta
3. Agregar 'UNION select 'qwerty'-- para ver si acepta texto
4. Agregar 'UNION select username,password from users-- para mostrar una tabla!


### Para Logins

* Agregar una comilla al final del usuario, si manda error: __ES VULNERABLE__

> Ahora agregar en usuario: Administrator' -- y poner cualquier password


### Blind SQL Injection

1. Abrir __Burp Suite__
2. Intercept __on__
3. Recargar sitio
4. Enviar a Repetidor
5. Agregar los siguientes payloads despues de el __TrackingId__
6. Oprimir Ctr+u
7. Oprimir botón __Enviar__
8. Insertar los codigos dentro de los paréntesis: ' || ()--

__Oracle__  dbms.pipe.receive_message(('a'),10)
__Microsoft__  WAITFOR DELAY '0:0:10'
__PostgreSQL__  SELECT pg_sleep(10)
__MySQL__  SELECT SLEEP(10)

### Authentication Vulnerability

1. Localizar el email de usuario
2. Abrir Burp Suite
3. Intercept __ON__
4. Poner cualquier password
5. Oprimir __Forward__ 
6. Identificar Solicitud de Autenticación
7. Botón derecho, elegir __Send to Intruder__
8. Seleccionar el texto del password y oprimir __Add__
9. Dejar __Sniper__ como tipo de ataque
10. Agrega (_Load_) el archivo de lista de palabras
11. Se instala en Kali Linux con: sudo apt-get install seclists
12. Se guardan en _/usr/share/wordlists/SecLists/Passwords/Common-Credentials/best1050.txt_
13. __Start attack__
14. Ordena por _length_ o por _Status code_ 
15. Si aparece el status __200__ será el password correcto


### Directory Traversal

1. Abrimos una imagen del sitio en una pestaña nueva
2. Abrimos __Burp Suite__
3. Capturamos la solicitud con Burp Suite (__Intercept on__)
4. Send to Repeater
5. Manipula el nombre del archivo con: /etc/passwd 
6. Si sale __No such file__, intenta con más profundidad: /../etc/passwd



### ------------------------------------------------------
##  ----- DOMINANDO SQL INJECTION -----
### ------------------------------------------------------

1. Crear cuenta en https://portswigger.net/web-security/all-labs
2. usar correo temporal en https://temp-mail.org/
3. Crear cuenta y guardar correo y password


### Payloads usados en SQL

> Mostrar todo
* or 1=1 -- -

> Probar cuántas columnas tiene la consulta
* order by 3
* union select 1,2,3

### Extrayendo informacion oculta

> Agregamos














