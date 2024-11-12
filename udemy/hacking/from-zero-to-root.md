# Hacking Etico web From Zero to Root

## CONFIGURACION


### Red de VM

> Instalar una maquina de Kali Linux
> __IMPORTANTE:__ Usar una red personalizada Red NAT
> Si se presentan problemas para que nos de red con NAT:
> sudo nano /etc/network/interfaces
> Agregamos bajo nuestra tarjeta de red:
> iface eth0 inet dhcp
> Ejecutamos en consola:
> sudo systemctl restart networking.service
> sudo service network-manager restart
> REINICIAR


### Actualizaciones

> sudo apt-get update
> sudo apt-get upgrade


## Burp Suite

1. Agregar el plugin para Firefox: __FoxyProxy__
2. Agregarle la IP: __127.0.0.1__
3. Puerto: __8080__
4. Esta configuración en Burp esta en Proxy - Options
5. Dar click en donde dice __Burp Suite__ en verde
6. __NECESITAMOS INSTALAR UN CERTIFICADO__
7. Entrar a: http://burp
8. Oprimir el botón __CA Certificate__
9. Ir a __Preferencias__
10. Buscar "certificate" y vamos a "View Certificate"
11. Oprimimos el botón __IMPORTAR__
12. Seleccionar el archivo del certificado
13. Marcar opciones: Confiar para websites y usuarios de correo
14. Entramos a una página, por ejemplo: wikipedia
15. Vemos que ya nos intercepta, le damos __FORWARD__

### POST / GET Y HTTPS / HTTP

1. Encendemos FoxyProxy en el Navegador
2. Checamos que nuestro __INTERCEPT__ esté encendido
3. Nos logueamos con credenciales falsas en __hack-yourself-first.com__
4. __EN BURP SUITE SE INTERCEPTA LA PETICIÓN__
5. Click derecho y send to __REPEATER__
6. Nos cambiamos a la pestaña __REPEATER__
7. Oprimimos __Send__
8. En la parte derecha, click derecho a __Show response in Browser__


### PortSwigger

1. Buscar los laboratorios de __Autenticación__
2. Entrar al lab: __Username enumeration via different responses__
3. Checar que este encendido el FoxyProxy en el Navegador
4. Checamos que nuestro __INTERCEPT__ esté encendido
5. Hacer intento de Login (_cualquier usuario y contraseña_)
6. Atacar con __INTRUDER__ (Ctrl+i)
7. Vamos a la pestaña de __Positions__
8. Oprimimos el boton __CLEAR__
9. Seleccionamos el texto (_campo_) del usuario
10. Oprimimos __Add__
11. Utilizaremos el ataque __Sniper__
12. Vamos a la pestaña __Payloads__
13. Elegimos __Lista simple__
14. Pegamos nuestra lista
15. Vamos a la pestaña de __Options__
16. Oprimimos __CLEAR__
17. Copiamos y Pegamos el mensaje de __Invalid username__
18. Oprimimos __Star Attack__
19. Observa usuarios que no tengan __Invalid username__
20. Repetir pasos para __password__

























































