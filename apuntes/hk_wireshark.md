# WIRESHARK

## Conceptos Basicos

> Herramienta para capturar, presentar y analizar trafico de red
> Necesita un _driver_ de capa de enlace para acceder a los datos

> Está basado en TCP/IP
> Los Routers dividen DOMINIOS DE BROADCAST
> Los Switches dividen DOMINIO DE COLISION

__Pantalla Inicial__

> En la pantalla de inicio se muestran las __INTERFACES__
> Cada interface muestra lineas de vida llamadas __SPARK LINES__


* __PANEL DE LISTA__
  > 1. __No__ - Número secuencial conforme se capturan los paquetes
  > 2. __Time__ - Tiempo transcurrido a partir de la primer captura
  > 3. __Source__ - IP origen
  > 4. __Destination__ - IP destino
  > 5. __Protocol__ - Protocolo de más alto nivel usado en el paquete
  > 6. __Length__ - Tamaño en Bytes del paquete
  > 7. __Info__ - La mayor información posible del paquete

* __PANEL DE DETALLES__
  > 1. __Metadata__
  > 2. __Capa de Enlace__
  > 3. __Capa de Red__
  > 4. __Capa de Transporte__
  > 5. __Capa de Aplicacion__

* __PANEL DE BYTES__
  > Muestra la información del paquete en __Hexadecimal__ y en __ASCII__

__Socket__

> Es el conjunto de una dirección IP y el puerto


## Agregar columnas

1. En el Panel de Detalles, seleccionamos un dato que necesitemos
2. Damos click con el __botón DERECHO__ sobre ese dato
3. Elegimos _"Apply as Column"_


## Quitar columnas

1. Para _eliminar_ - Botón Derecho - Eliminar
2. Para __ocultar__ - Botón Derecho Encabezado - Quitar Selección


## Aislar columnas

1. Primero creamos una columna nueva, Ej. Host
2. Damos __DOBLE CLICK__ al encabezado para ordenarlas
3. Ahora estan juntos los paquetes que tengan contenido en Host


## Disectores

> Es un componente que interpreta y muestra los datos de un protocolo específico

1. __Método Estático__ - Interpreta los _números de puerto_ conocidos en la capa de transporte
2. __Método Heurístico__ - Intenta adivinar el protocolo en un _puerto no-estándar_
3. __Método Manual__ - Lo asignamos un protocolo por medio de _Decode As_




## Filtros

```bash
ip.src==192.168.0.0/16
ip.src==192.168.0.0/16 and ip.dst==192.168.0.0/16
tcp.port eq 25 or icmp
```

