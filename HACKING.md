<h1 style="color:#219ebc">Hacking</h1>

- [CONCEPTOS](#conceptos)
- [Reconnaissance: Footprinting Pasivo](#reconnaissance-footprinting-pasivo)
- [Reconnaissance: Footprinting Activo (ESCANEO)](#reconnaissance-footprinting-activo-escaneo)
  - [Por medio del protocolo ICMP](#por-medio-del-protocolo-icmp)
  - [Por medio de ARP](#por-medio-de-arp)
  - [Escaneo compuesto con NMAP](#escaneo-compuesto-con-nmap)
  - [Otras opciones de NMap](#otras-opciones-de-nmap)
  - [Plantillas de Tiempo en NMap](#plantillas-de-tiempo-en-nmap)
  - [Escaneo de puertos FILTRADO](#escaneo-de-puertos-filtrado)
  - [Escanear SO de manera agresiva](#escanear-so-de-manera-agresiva)
  - [NSE](#nse)
  - [Registros DNS](#registros-dns)
  - [Enumeración SNMP](#enumeración-snmp)
  - [WPScan para Wordpress](#wpscan-para-wordpress)
- [Wireshark](#wireshark)
  - [Filtrar por IP](#filtrar-por-ip)

# CONCEPTOS

__DHCP__ Dynamic Host Configuration Protocol <br/>
__NAT__ Network Address Translation <br/>
__DNS__ Domain Name Server <br/>
__ARP__ Address Resolution Protocol <br/>
__ICMP__ Internet Control Message  - Usa ping o traceroute<br/> 
<br/>

__IPS__ - Intrusion Prevention System <br/>
__IDS__ - Intrusion Detection System <br/>
<br/>

| Puerto | Servicio | 
| :---: | :---: | 
| 22 | __SSH__ | 
| 80 | __HTTP__ | 

__Target__ - Organización, Servidor, persona o cualquier objeto de interés.<br/> 
__LFI__ - Inclusión de archivos locales.<br/> 
__RFI__ - Inclusión de archivos remotos.<br/> 
__RCE__ - Ejecución remota de código.<br/> 
__DoS__ - ATAQUE de Denegación de Servicios.<br/> 


# Reconnaissance: Footprinting Pasivo

- [x] Es cuando recopilamos la mayor cantidad de __INFORMACION__ posible.
- [x] El target no de da cuenta que se está recopilando información.
- [x] Se utiliza el __OSINT__: Open Source Intelligence.


* Dominio, Registros y Servidores DNS por medio de __whois__
* Tecnologías (por medio de vacantes de empleo o la web)
* Información de usuarios (por medio de redes sociales o publicaciones)


# Reconnaissance: Footprinting Activo (ESCANEO)

## Por medio del protocolo ICMP

- [x] Usamos __ping sweep__

```fping -a -g 192.168.10.0/24 2> /dev/null```

- [x] __-a__ PARA DETECTAR HOSTS ACTIVOS
- [x] __-g__ GENERA UNA LISTA DE TARGETS
- [x] __2> /dev/null__ QUITA LOS ERRORES


## Por medio de ARP

```sudo netdiscover -r 192.168.132.0/24```

- [x] __-r__ RANGO
- [x] __-r__ RANGO


## Escaneo compuesto con NMAP

```sudo nmap -sn 192.168.1.254 -T4```

- [x] __-sn__ No Port Scan
- [x] __-T4__ Es el tiempo que espera
- [x] En una red local, ejecutará __ARP__

```sudo nmap -sn 192.168.1.254 -T4 --disable-arp```

- [x] __--disable-arp__ deshabilita el protocolo __ARP__


## Otras opciones de NMap

| Parámetro | Escaneo | 
| :---: | :---: | 
| -sS | TCP SYN Scan | 
| -sT | TCP Connect Scan | 
| -sU | UDP Scan | 
| -sV | detección de Versiones | 


## Plantillas de Tiempo en NMap

| Plantilla | Velocidad | Descripción | 
| :---: | :---: | :---: | 
| T0 | __Paranoid__ | Extremadamente lento para evitar detecciones |
| T1 | __Sneaky__ | Lento y sigiloso |
| T2 | __Polite__ | Más lento pero menos carga en la red |
| T3 | __Normal__ | Por Defecto|
| T4 | __Aggressive__ | Más rápido, pero necesita un host o red confiable |
| T5 | __Insane__ | El más rápido, muy ruidos, alto riesgo de falsos negativos|

__OS Fingerprinting__ <br/>

> Proceso para determinar el Sistema Operativo de un dispositivo en la red<br/>
<br/>

```sudo nmap -O 10.1.1.1```

__Banner Grabbing__ <br/>

> Proceso para identificar el software de un equipo en la red
<br/>

```sudo nmap -sV 10.1.1.1```

__Agressive__ <br/>

> Hace la función de detección de SO, versiones, scripts y Traceroute

* Tardará en ejecutarse
* Generará mucho tráfico
* Puede tronar servicios

```sudo nmap -A 10.1.1.1```

## Escaneo de puertos FILTRADO

- [x] Mandamos a un archivo los puertos encontrados:

```sudo nmap -sS 192.168.132.132 -p- -T4 --open -oN puertos.txt```

- [x] Vamos a FILTRAR de ahí solo los números de puerto 
- [x] Las líneas con puertos tienen en comun la palabra **open**
- [x] Filtramos por medio de __grep__:

```cat puertos.txt | grep "open"```

- [x] Podemos cortar en 2 con el comando __cut__ delimitado por "/"
- [x] Y mostrar solo la primer fila:

```cat puertos.txt | grep "open" | cut -d "/" -f 1```

- [x] Necesitamos reemplazar el texto de **enter** por una coma
- [x] Usamos el comando __tr__

```cat puertos.txt | grep "open" | cut -d "/" -f 1 | tr '\n' ','```

- [x] Nos queda una coma al final, la quitamos con el comando __sed__:

```cat puertos.txt | grep "open" | cut -d "/" -f 1 | tr '\n' ',' | sed 's/.$//'```

- [x] Se utilizó una __expresión regular__
- [x] Donde __.__ es cualquier caracter
- [x] Y __$__ es el FINAL de la línea
- [x] Lo podemos mandar a un archivo agregando ```> puertos_filtrados.txt```
- [x] Ya que tenemos los puertos separados por coma en un archivo, ejecutamos:

```sudo nmap -sV 192.168.132.132 -p $(cat puertos_filtrados.txt) -T4```

- [x] Para que se ejecute un comando dentro de otro comando usamos: __$()__

## Escanear SO de manera agresiva

```sudo nmap -O --osscan-guess 192.168.132.132 -T4```


## NSE

- [x] Actualizar Nmap

```sudo apt update``` <br/>
```sudo apt install nmap``` <br/>

- [x] Ver scripts de ssh y de http

```ls -1 /usr/share/nmap/scripts/ssh*``` <br/>
```ls -1 /usr/share/nmap/scripts/http*``` <br/>

- [x] Otra manera de listar scripts **NSE**

```sudo updatedb``` <br/>
```locate *http*.nse``` <br/>

- [x] Ver descripción de un script:

```nmap --script-help=ftp-anon``` <br/>

> Donde __--script-help__ nos muestra la ayuda
> y __ftp-anon__ es el script a mostrar

* __safe__ es seguro y no TRUENA servicios
* __intrusive__ o __dos__ debemos tener cuidado al ejecutarlos
* __auth__ pide credenciales de sesion

- [x] Ejecutar un script __NSE__

```sudo nmap --script=http-enum 192.168.1.1 -p 80``` <br/>

## Registros DNS

| Tipo | Descripción | 
| :---: | :---: | 
| A | Dirección IPv4 de un host | 
| AAAA | Dirección IPv6 de un host | 
| MX | Servidores de Correo de un dominio | 
| CNAME | Canonical Name de un Alias de dominio | 
| NS | DNS responsables de la zona | 
| SOA | __Start of Authority__ para información para la zona | 
| PTR | Regresa el __Hostname__ de una dirección IP | 

## Enumeración SNMP

* __Simple Network Management Protocol__ 

> Recopila información sobre dispositivos de red
> y utiliza el puerto __UDP 161__
<br/>

> Consiste de 3 elementos:

- [x] Dispositivo administrado
- [x] __Agente__ (Software en el dispositivo)
- [x] __NMS__ Software que administra los nodos

* __MIB__ Management Information Base

> Base de Datos con información del Nodo <br/>
> Es una tabla estructurada con valores devueltos por el agente
<br/>

* __Community__ Strings

> Es como una contraseña que permite acceso al nodo

```snmpwalk -c public -v1 192.168.1.1``` <br/>

## WPScan para Wordpress

- [x] Actualizar base de datos primero

```wpscan --update``` <br/>


- [x] Escaneo default de manera NO intrusiva

```wpscan --url <URL del target>``` <br/>


- [x] Escaneo default de manera NO intrusiva con __token__

```wpscan --url <URL del target> --api-token <token>``` <br/>

- [x] Enumeraciones:

| Tipo | Descripción | 
| :---: | :---: | 
| p | Escanea solo plugins populares | 
| vp | Escanea solo plugins conocidos como vulnerables | 
| ap | Escanea TODOS los plugins | 
| t | Escanea solo temas populares | 
| vt | Escanea solo temas conocidos como vulnerables | 
| at | Escanea TODOS los temas | 


- [x] Escaneo **AGRESIVO** con __token__

```wpscan --url http://10.0.0.48 --enumerate ap,at --plugins-detection aggressive --themes-detection aggressive --token-api <token>``` <br/>


- [x] Opciones de configuración:

```wpscan --hh``` <br/>








<br/><br/><br/>

# Wireshark

## Filtrar por IP

```ip.addr==192.168.1.254```













