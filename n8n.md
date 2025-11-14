<h1 style="color:#c1121f">n8n</h1>

# Introducción

- [x] __CONECTA__ diferentes apps que normalmente no trabajan juntas
- [x] Es de código abierto
- [x] No se necesita escribir código
- [x] Se puede instalar en nuestro equipo o servidor

## Automatización

> Es cualquier proceso que realiza tareas por sí solas,
> sin tener que hacerlas manualmente, ahorrando tiempo y evitando errores.


## Flujo de Trabajo

> Conjunto de __PASOS__ conectados que definen cómo trabaja la __automatización__

- [x] Eliges un __trigger__ (_como recibir un email_)
- [x] Agregas una serie de __acciones__ 
- [x] Puedes conectar varios __nodos__ o pasos entre sí

## Agente IA

> Herramienta inteligente de automatización para:

1. Tomar __decisiones__
2. Entender lenguaje
3. Mantener una conversación
4. __Analizan__ mensajes
5. Entienden la __intención__ del usuario
6. Responde a preguntas complejas
7. Se __adapta__ a nueva información o cambio de situación

# Instalación

1. Desde el sitio web

- [x] Comenzar prueba gratuita
- [x] Podemos crear carpetas de proyectos
- [x] Crear flujo de trabajo

2. Instalarlo en nuestro servidor

- [x] __DOCKER__

```bash
docker volume create n8n_data
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```
- [x] __NODE__ 

* Instalar
```npx n8n```

* Ejecutar
```n8n```

* Actualizar
```npm update -g n8n```


3. Herramientas de terceros

- [x] Podemos usar Hostinger


# API

* Application Programming Interface

- [x] Expone un __servicio__
- [x] Los Desarrolladores crean __programas__ 
- [x] Los programas se usan para __consumirlo__

## HTTP Status Code

1xx - Un momento
2xx - Aqui tienes
3xx - Largo de aqui
4xx - Fue tu culpa
5xx - Fue nuestra culpa

* Ejemplos

- [x] __200__ Ok
- [x] __401__ Unauthorized
- [x] __404__ Not Found
- [x] __500__ Internal Server Error

# Webhooks

- [x] Si esperamos a que pase algo
- [x] Requerimos información de un servicio

# NODOS

## Categorías

1. Entry Point
2. Función
3. End Point

## Tipos

1. Triggers
2. Acciones en una App
3. Transformación de Datos
4. Flujo
5. Archivos

## Parámetros

1. Credenciales
2. Recursos
3. Operación
4. Configuración

<div style="color:#AE445A">

# AUTOMATIZACIONES

</div>

## Telegram + IA

1. Instalar aplicación de __Telegram__
2. Buscar __BotFather__
3. Escribimos ```/newbot```
4. Darle un nombre
5. Agregar un usuario que termine con ```_bot```
6. Copiar __API Key__
7. Agregarlo como __Access Token__
8. Agregar __AI Agent__
9. Configurar como __Define Below__
10. Arrastrar el campo __text__ a prompt
11. Agregar respuesta __telegram__
12. Agregar el __ID__ en Chat ID
13. Agregar __output__ en text



