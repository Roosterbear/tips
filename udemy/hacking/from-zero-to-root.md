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


























































