# I am the 👁️  in the sky 🔓

## tryhackme.com

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



## Gathering

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

## Burp Suite

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






# check

Restart-Computer -ComputerName "172.16.33.10" -Force