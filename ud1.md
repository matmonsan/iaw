---
title: UD 1. Introducción al entorno de desarrollo, los servidores de aplicaciones Web y sus funcionalidades.
description: "<strong>Profesor:</strong> Matías Montávez Sánchez | <strong>Módulo:</strong> Implantación de Aplicaciones web"
---
[⌂ Volver al inicio](index.md)

## Índice

- [1. Introducción a la implantación de aplicaciones web](#1-introducción-a-la-implantación-de-aplicaciones-web)
- [2. Objetivos de la unidad](#2-objetivos-de-la-unidad)
- [3. Criterios de evaluación](#3-criterios-de-evaluación)
- [4. Entorno de desarrollo](#4-entorno-de-desarrollo)
- [5. Cliente y servidor](#5-cliente-y-servidor)
- [6. Servidores web y servidores de aplicaciones](#6-servidores-web-y-servidores-de-aplicaciones)
- [7. Funcionamiento de una aplicación web](#7-funcionamiento-de-una-aplicación-web)
- [8. Protocolos HTTP y HTTPS](#8-protocolos-http-y-https)
- [9. Herramientas y tecnologías habituales](#9-herramientas-y-tecnologías-habituales)
- [10. Comandos básicos de Linux](#10-comandos-básicos-de-linux)
- [11. Instalación y configuración del entorno](#11-instalación-y-configuración-del-entorno)
- [12. Despliegue y explotación básica](#12-despliegue-y-explotación-básica)
- [13. LAMP Stack en Ubuntu Server](#13-lamp-stack-en-ubuntu-server)
- [14. Proyecto final: instalación y documentación de una pila LAMP](#14-proyecto-final-instalación-y-documentación-de-una-pila-lamp)

---

## 1. Introducción a la implantación de aplicaciones web

La implantación de aplicaciones web consiste en preparar y poner a disposición de los usuarios una aplicación desarrollada para ejecutarse en un entorno web. Para ello, es necesario instalar los componentes correctos, configurar los servicios necesarios y verificar que la aplicación funciona de forma correcta y segura.

Una aplicación web no se limita a escribir código. También incluye la elección del servidor adecuado, la configuración de la red, el acceso a la base de datos, la seguridad, la disponibilidad y el mantenimiento posterior. La implantación es una parte fundamental del ciclo de vida de una aplicación, porque es el momento en el que el sistema deja de estar solo en el entorno de desarrollo y pasa a ser usado por usuarios reales.

La implantación requiere tener en cuenta aspectos como:

- el tipo de aplicación que se va a desplegar;
- la arquitectura de cliente y servidor;
- la gestión de recursos y permisos;
- la compatibilidad del software;
- la seguridad de la información;
- la monitorización del sistema y la resolución de errores.

Por tanto, no basta con programar, sino que hay que saber cómo dejar la aplicación operativa en un entorno real.

---

## 2. Objetivos de la unidad

En esta unidad se pretende que el alumnado conozca el entorno de trabajo necesario para desarrollar e implantar aplicaciones web y comprenda la función de los servidores web, los servidores de aplicaciones y los servicios asociados en la ejecución de una aplicación.

Los objetivos principales son:

- Conocer los elementos básicos del entorno de desarrollo web.
- Comprender la diferencia entre cliente, servidor, aplicación y base de datos.
- Identificar las funciones de un servidor web y de un servidor de aplicaciones.
- Analizar el flujo de una petición HTTP y la respuesta generada por el servidor.
- Entender el papel de la configuración y el despliegue en la implantación de una aplicación.
- Reconocer los requisitos necesarios para alojar y mantener una aplicación web.
- Evaluar qué herramientas y tecnologías son adecuadas para un entorno concreto.
- Realizar una pequeña configuración básica para ejecutar una aplicación web localmente.

---

## 3. Criterios de evaluación

Se evaluará que el alumnado sea capaz de:

- Definir qué es un entorno de desarrollo web y cuáles son sus componentes principales.
- Diferenciar entre un servidor web, un servidor de aplicaciones y una base de datos.
- Explicar la arquitectura cliente-servidor y el flujo de trabajo de una aplicación web.
- Describir el funcionamiento del protocolo HTTP y sus principales códigos de respuesta.
- Configurar un entorno local básico para el uso de una aplicación web.
- Analizar qué servicios son necesarios para la implantación de una aplicación.
- Relacionar la tecnología utilizada con el tipo de aplicación o servicio que se desea desplegar.
- Redactar una explicación clara y ordenada sobre la configuración o despliegue de un sistema web.
- Identificar errores básicos de funcionamiento y soluciones elementales de configuración.

La evaluación de esta unidad se basará tanto en la comprensión conceptual como en la aplicación práctica de esos conocimientos en ejercicios y proyectos sencillos.

---

## 4. Entorno de desarrollo

El entorno de desarrollo es el conjunto de herramientas, programas y recursos necesarios para desarrollar aplicaciones. En el caso de aplicaciones web, este entorno suele incluir lo siguiente:

- un ordenador o máquina de trabajo;
- un sistema operativo compatible;
- un editor de texto o IDE (Visual Studio Code, Eclipse, NetBeans, IntelliJ, etc.);
- un navegador web para probar la aplicación;
- un servidor local o de pruebas;
- un intérprete o entorno de ejecución del lenguaje utilizado;
- herramientas de gestión de dependencias y paquetes;
- un sistema de control de versiones como Git;
- una base de datos si la aplicación la requiere;
- herramientas de depuración y monitorización.

El entorno de desarrollo no es solo un programa aislado, sino un conjunto coordinado de piezas que permiten programar, probar, depurar y finalmente implantar la aplicación.

### Elementos principales del entorno

1. Cliente
   El cliente es el usuario o el navegador que accede a la aplicación. El navegador interpreta HTML, CSS y JavaScript y presenta la interfaz al usuario.

2. Servidor
   El servidor es la máquina o programa que recibe las peticiones del cliente, procesa la información y devuelve una respuesta. Puede ser web, de aplicaciones o de base de datos.

3. Aplicación
   Es el código que implementa la lógica de negocio: formularios, autenticación, gestión de usuarios, consultas, etc.

4. Base de datos
   Se utiliza para guardar información persistente: usuarios, productos, facturas, registros, horarios, etc.

5. Red y protocolos
   El cliente y el servidor se comunican mediante protocolos de red, especialmente HTTP y HTTPS.

---

## 5. Cliente y servidor

La arquitectura cliente-servidor es el modelo que se utiliza en la mayoría de aplicaciones web. En este modelo:

- el cliente solicita información o servicios;
- el servidor procesa la solicitud;
- el cliente recibe la respuesta y la muestra.

Este flujo es fundamental para comprender el funcionamiento de Internet y de las aplicaciones web.

### Cliente

El cliente es la parte que inicia la interacción. Generalmente es un navegador, aunque también puede ser una aplicación móvil o un servicio externo que realiza peticiones. Su papel es enviar una solicitud y mostrar el resultado recibido.

### Servidor

El servidor es el encargado de atender esas solicitudes. Puede ofrecer recursos estáticos, ejecutar scripts, acceder a bases de datos o combinar distintas operaciones para generar la respuesta final.

### Ejemplo sencillo

Cuando una persona entra en una página web:

- escribe la dirección en el navegador;
- el navegador solicita la página al servidor;
- el servidor identifica la petición;
- localiza el recurso o ejecuta la lógica requerida;
- devuelve la respuesta;
- el navegador muestra el contenido al usuario.

---

## 6. Servidores web y servidores de aplicaciones

### 6.1 Servidor web

Un servidor web es un programa o conjunto de programas diseñado para atender peticiones HTTP. Su función principal es servir contenido al cliente, normalmente páginas HTML, archivos CSS, JavaScript, imágenes, vídeos y otros recursos estáticos.

Ejemplos de servidores web son:

- Apache HTTP Server
- Nginx
- IIS (Internet Information Services)

Sus funciones más importantes son:

- recibir peticiones del navegador;
- localizar archivos o recursos demandados;
- atender respuestas HTTP;
- gestionar rutas y directorios;
- servir contenido estático;
- controlar errores básicos de acceso.

Un servidor web, por sí solo, no suele ejecutar toda la lógica de negocio de una aplicación compleja. Para ello se utiliza un servidor de aplicaciones.

### 6.2 Servidor de aplicaciones

Un servidor de aplicaciones es un entorno de ejecución diseñado para desplegar y ejecutar aplicaciones dinámicas. Se encarga de procesar la lógica del negocio, gestionar usuarios, sesiones, seguridad y acceso a bases de datos.

Su objetivo es proporcionar un entorno donde la aplicación puede ejecutarse, gestionando recursos, conexiones y procesos de forma segura y eficiente.

Ejemplos de servidores de aplicaciones son:

- Tomcat
- WildFly
- GlassFish
- Jetty
- Node.js con Express
- servidores Java EE o J2EE

### 6.3 Funciones principales del servidor de aplicaciones

- Ejecutar código de la aplicación.
- Generar páginas dinámicas en función de la entrada del usuario.
- Interactuar con la base de datos.
- Gestionar sesiones y autenticación.
- Integrar frameworks y librerías.
- Controlar la seguridad y la autorización.
- Mejorar la escalabilidad y el rendimiento.

### 6.4 Diferencias entre servidor web y servidor de aplicaciones

El servidor web se centra en servir contenido y atender peticiones HTTP. El servidor de aplicaciones se centra en ejecutar la lógica de la aplicación y ofrecer servicios para que esta funcione correctamente.

En una arquitectura típica:

- el cliente solicita una URL;
- el servidor web recibe la petición;
- si la petición requiere lógica compleja, la reenvía al servidor de aplicaciones;
- el servidor de aplicaciones ejecuta el código y consulta la base de datos;
- devuelve el resultado al servidor web;
- el servidor web responde al navegador.

### 6.5 Relación entre ambos

Es muy común que ambos servidores trabajen conjuntamente. La separación de funciones aporta varias ventajas:

- mejor organización del sistema;
- mayor seguridad;
- mayor escalabilidad;
- mejor mantenimiento;
- distribución de tareas según responsabilidad.

En este esquema se aprovecha la rapidez del servidor web para servir recursos estáticos y la potencia del servidor de aplicaciones para manejar la lógica.

---

## 7. Funcionamiento de una aplicación web

Una aplicación web realiza el siguiente proceso básico:

1. El usuario accede a la URL desde el navegador.
2. El navegador genera una solicitud HTTP.
3. El servidor web recibe la petición.
4. La petición se procesa por la aplicación o por el servidor de aplicaciones.
5. Si es necesario, la aplicación consulta la base de datos.
6. Se genera una respuesta con el contenido solicitado o con un error.
7. El navegador interpreta la respuesta y la muestra al usuario.

### 7.1 Petición HTTP

La petición HTTP contiene información necesaria para que el servidor pueda responder. Algunos elementos fundamentales son:

- método o verbo HTTP: GET, POST, PUT, DELETE, etc.;
- URL: dirección del recurso solicitado;
- cabeceras: información adicional sobre el cliente, idioma, cookies, tamaño de la respuesta, etc.;
- cuerpo: datos enviados en la solicitud, principalmente con POST o PUT.

### 7.2 Respuesta HTTP

Una vez procesada la petición, el servidor devuelve una respuesta. Esta respuesta contiene:

- código de estado;
- cabeceras con información de la respuesta;
- cuerpo con el contenido solicitado, que puede ser HTML, JSON, XML, texto o archivos.

### 7.3 Códigos de estado más habituales

- 200 OK: la solicitud se ha realizado correctamente.
- 201 Created: el recurso se ha creado correctamente.
- 301 Moved Permanently: el recurso ha sido movido permanentemente.
- 404 Not Found: el recurso no existe o no se encuentra.
- 500 Internal Server Error: error interno del servidor.
- 403 Forbidden: el acceso está prohibido.
- 401 Unauthorized: falta autenticación o autorización.

Estos códigos permiten diagnosticar si la petición se ha completado con éxito o si hay un problema de configuración, de acceso o de ejecución.

---

## 8. Protocolos HTTP y HTTPS

### 8.1. El Protocolo HTTP (HyperText Transfer Protocol)

El **Protocolo de Transferencia de Hipertexto** (HTTP) es el protocolo de comunicación de la capa de aplicación utilizado como base para el intercambio de información en la *World Wide Web*. Funciona mediante un modelo **Cliente-Servidor**, donde el cliente (generalmente un navegador web) realiza peticiones (*requests*) y el servidor responde (*responses*) con los recursos solicitados (archivos HTML, imágenes, JSON, estilos CSS, etc.).

#### Características principales de HTTP

* **Sin estado (*Stateless*):** El protocolo no guarda ningún estado de las transacciones anteriores por sí mismo. Cada petición es independiente. Para mantener la sesión del usuario se recurre a mecanismos adicionales como *cookies*, tokens (JWT) o sesiones de servidor.

* **Orientado a peticiones y respuestas:** Todas las solicitudes y respuestas siguen una estructura prefijada en formato de texto plano (con soporte para transferencia de datos binarios en el cuerpo).

* **Puerto por defecto:** Utiliza por defecto el **puerto 80** mediante el protocolo de transporte TCP.

* **Soporte para múltiples tipos de contenido:** A través del uso de cabeceras MIME (*Multipurpose Internet Mail Extensions*), puede transferir cualquier tipo de medio (texto, imágenes, vídeos, datos estructurados, etc.).

### 8.2. Estructura de Mensajes HTTP

#### 8.2.1. Estructura de una Petición HTTP (*Request*)

Una petición enviada por el cliente consta de tres partes fundamentales:

1. **Línea de petición (*Request Line*):**

   * **Método HTTP:** Acción a realizar (ej. `GET`, `POST`, `PUT`).

   * **URI/Path:** Ruta del recurso solicitado (ej. `/api/usuarios?id=5`).

   * **Versión del protocolo:** (ej. `HTTP/1.1` o `HTTP/2`).

2. **Cabeceras de petición (*Headers*):** Pares clave-valor que proporcionan metadatos sobre la petición y el cliente.

   * `Host`: Nombre del servidor de destino (ej. `www.ejemplo.com`).

   * `User-Agent`: Información del navegador o cliente que realiza la consulta.

   * `Accept`: Tipos de contenido que el cliente puede procesar (ej. `application/json`, `text/html`).

   * `Authorization`: Credenciales o tokens de autenticación.

   * `Content-Type`: Tipo de datos enviados en el cuerpo de la petición.

3. **Cuerpo de la petición (*Body*):** Datos adicionales enviados al servidor (opcional, típico en métodos como `POST`, `PUT` y `PATCH`).

#### 8.2.2. Estructura de una Respuesta HTTP (*Response*)

Una respuesta enviada por el servidor al cliente consta de:

1. **Línea de estado (*Status Line*):**

   * **Versión del protocolo:** (ej. `HTTP/1.1`).

   * **Código de estado (*Status Code*):** Número entero de 3 dígitos (ej. `200`, `404`).

   * **Texto de estado (*Reason Phrase*):** Descripción corta legible por humanos (ej. `OK`, `Not Found`).

2. **Cabeceras de respuesta (*Headers*):** Metadatos proporcionados por el servidor.

   * `Content-Type`: Formato del recurso devuelto en la respuesta.

   * `Content-Length`: Tamaño de la respuesta en bytes.

   * `Set-Cookie`: Instrucción para que el navegador almacene una cookie.

   * `Server`: Información sobre el software del servidor web.

3. **Cuerpo de la respuesta (*Body*):** Contenido del recurso solicitado (código HTML, objeto JSON, datos binarios de una imagen, etc.).

### 8.3. Tipos de Peticiones HTTP (Métodos HTTP)

Los métodos HTTP indican la acción que se desea realizar sobre el recurso identificado por la URI.

| Método | Descripción | ¿Envía Body? | Idempotente | Seguro | 
 | ----- | ----- | ----- | ----- | ----- | 
| **GET** | Solicita una representación del recurso especificado. No modifica el estado del servidor. | No | Sí | Sí | 
| **POST** | Envía datos al servidor para crear un nuevo recurso o procesar una entidad. | Sí | No | No | 
| **PUT** | Reemplaza totalmente el recurso de destino con la información enviada. | Sí | Sí | No | 
| **PATCH** | Aplica modificaciones parciales a un recurso existente. | Sí | No | No | 
| **DELETE** | Elimina el recurso especificado en la URI. | Opcional | Sí | No | 
| **HEAD** | Solicita una respuesta idéntica a `GET` pero sin el cuerpo de la respuesta. | No | Sí | Sí | 
| **OPTIONS** | Describe las opciones de comunicación/métodos permitidos para el recurso (usado en CORS). | No | Sí | Sí | 

* **Método Seguro (*Safe*):** No modifica el estado del recurso en el servidor (ej. `GET`, `HEAD`, `OPTIONS`).

* **Método Idempotente:** Realizar la misma petición varias veces consecutivas produce exactamente el mismo resultado en el servidor que realizarla una sola vez (ej. `GET`, `PUT`, `DELETE`).

### 8.4. Códigos de Estado HTTP

Los códigos de estado informan al cliente sobre el resultado de la petición. Se dividen en 5 clases:

#### 1xx: Respuestas Informativas

* **100 Continue:** El servidor ha recibido las cabeceras iniciales y el cliente debe continuar enviando el cuerpo de la petición.

#### 2xx: Respuestas Satisfactorias

* **200 OK:** La petición se ha completado con éxito.

* **201 Created:** La petición se ha completado correctamente y se ha creado un nuevo recurso.

* **204 No Content:** La petición ha tenido éxito pero no hay contenido que devolver en la respuesta.

#### 3xx: Redirecciones

* **301 Moved Permanently:** El recurso solicitado se ha movido de forma permanente a una nueva URL.

* **302 Found / Temporary Redirect:** El recurso está ubicado temporalmente en otra ubicación.

* **304 Not Modified:** El recurso no ha sido modificado desde la última petición (se utiliza para optimizar la caché del navegador).

#### 4xx: Errores del Cliente

* **400 Bad Request:** La petición contiene una sintaxis inválida o no puede ser procesada.

* **401 Unauthorized:** Requiere autenticación previa del usuario.

* **403 Forbidden:** El cliente no tiene permisos suficientes para acceder al recurso.

* **404 Not Found:** El servidor no encuentra el recurso solicitado.

* **405 Method Not Allowed:** El método HTTP utilizado no está permitido para este recurso.

* **422 Unprocessable Entity:** La sintaxis es correcta pero existen errores de validación lógica en los datos.

#### 5xx: Errores del Servidor

* **500 Internal Server Error:** Error genérico dentro de la lógica del servidor.

* **502 Bad Gateway:** El servidor actuaba como proxy o pasarela y recibió una respuesta inválida del servidor de origen.

* **503 Service Unavailable:** El servidor no está disponible actualmente (por sobrecarga o mantenimiento).

* **504 Gateway Timeout:** La pasarela o proxy agotó el tiempo de espera aguardando la respuesta del servidor interno.

### 8.5. El Protocolo HTTPS (HyperText Transfer Protocol Secure)

**HTTPS** es la versión segura y cifrada del protocolo HTTP. Utiliza los protocolos de seguridad **TLS (Transport Layer Security)** o su predecesor **SSL (Secure Sockets Layer)** para establecer un canal de comunicación cifrado entre el cliente y el servidor.

#### Características clave de HTTPS

* **Puerto por defecto:** Utiliza el **puerto 443**.

* **Cifrado de datos:** Combina dos tipos de cifrado:

  * **Cifrado Asimétrico (Clave pública/privada):** Se utiliza durante la fase inicial de negociación (*TLS Handshake*) para autenticar al servidor y acordar de forma segura una clave secreta compartida.

  * **Cifrado Simétrico:** Se utiliza para cifrar y descifrar el tráfico de datos durante la sesión activa mediante la clave secreta compartida, garantizando alta velocidad.

#### Garantías de Seguridad de HTTPS

1. **Confidencialidad:** Evita que terceros puedan interceptar e interpretar el tráfico transmitido (*eavesdropping* o ataque *Man-in-the-Middle*).

2. **Integridad:** Asegura que los datos transmitidos no hayan sido alterados o manipulados en el trayecto.

3. **Autenticidad:** Valida la identidad del sitio web mediante un **Certificado Digital SSL/TLS** firmado por una **Autoridad de Certificación (CA)** reconocida.

### 8.6. Comparativa entre HTTP y HTTPS

| Característica | HTTP | HTTPS | 
 | ----- | ----- | ----- | 
| **Seguridad** | Transmisión en texto plano (sin cifrar) | Transmisión cifrada (SSL/TLS) | 
| **Puerto por defecto** | 80 | 443 | 
| **Certificado de Seguridad** | No requiere | Requiere certificado digital válido firmado por CA | 
| **Integridad de datos** | Vulnerable a interceptación y modificación | Protegido frente a manipulaciones | 
| **Posicionamiento y confianza** | Advertencia de "No seguro" en navegadores | Estándar actual favorecido por buscadores (SEO) | 

---

## 9. Herramientas y tecnologías habituales

En el desarrollo e implantación de aplicaciones web se utilizan muchas herramientas. Algunas de las más habituales son:

### 9.1 Editores e IDE

- Visual Studio Code
- IntelliJ IDEA
- NetBeans
- Eclipse

Estos programas facilitan la escritura, depuración y organización del código.

### 9.2 Lenguajes y tecnologías web

- HTML: estructura y contenido de la página.
- CSS: diseño, estilo y presentación visual.
- JavaScript: lógica del cliente y comportamiento dinámico.
- PHP, Java, Python, .NET: lenguajes para la lógica del lado del servidor.
- SQL: lenguaje para consultar y manipular bases de datos.

### 9.3 Herramientas de soporte

- Git y GitHub para control de versiones.
- Maven, Gradle, npm y Composer para gestión de dependencias.
- Docker para encapsular y distribuir aplicaciones.
- Postman para probar APIs.
- navegadores con herramientas de desarrollo para depurar y analizar el comportamiento.

### 9.4 Bases de datos

Muchas aplicaciones web requieren almacenamiento persistente. Entre las bases de datos más comunes están:

- MySQL
- PostgreSQL
- MariaDB
- SQL Server
- MongoDB

La base de datos permite guardar y recuperar información de forma organizada y segura.

---

## 10. Comandos básicos de Linux

### 10.1 `ls` - Listar archivos y directorios
El comando `ls` se utiliza para listar el contenido de un directorio.

**Sintaxis:**
```bash
ls [opciones] [directorio]
```

**Opciones más comunes:**
- `-l`: Lista en formato largo, mostrando permisos, propietario, tamaño, etc.
- `-a`: Muestra todos los archivos, incluidos los ocultos (comienzan con `.`).
- `-h`: Muestra los tamaños en formato legible (KB, MB, GB).
- `-R`: Lista de manera recursiva los archivos de los subdirectorios.

**Ejemplos:**
```bash
ls
ls -l /home/user/
ls -la
ls -lh /var/log/
```

---

### 10.2 `cd` - Cambiar de directorio
El comando `cd` permite moverte entre directorios.

**Sintaxis:**
```bash
cd [directorio]
```

**Opciones comunes:**
- `cd ..`: Retrocede al directorio anterior.
- `cd`: Va al directorio home del usuario.

**Ejemplos:**
```bash
cd /etc
cd
cd ~
```

---

### 10.3 `pwd` - Mostrar el directorio actual
El comando `pwd` (print working directory) muestra la ruta del directorio actual en el que te encuentras.

**Sintaxis:**
```bash
pwd
```

**Ejemplo:**
```bash
pwd
```

---

### 10.4 `cp` - Copiar archivos y directorios
El comando `cp` copia archivos o directorios de una ubicación a otra.

**Sintaxis:**
```bash
cp [opciones] origen destino
```

**Opciones más comunes:**
- `-r`: Copia recursivamente un directorio.
- `-i`: Solicita confirmación antes de sobrescribir archivos.
- `-u`: Solo copia si el archivo fuente es más reciente o no existe en el destino.

**Ejemplos:**
```bash
cp archivo.txt /home/user/
cp -r /home/user/carpeta /backup/
```

---

### 10.5 `mv` - Mover o renombrar archivos y directorios
Este comando mueve archivos o directorios de una ubicación a otra, o los renombra.

**Sintaxis:**
```bash
mv [opciones] origen destino
```

**Opciones más comunes:**
- `-i`: Solicita confirmación antes de sobrescribir.
- `-u`: Solo mueve si el archivo fuente es más reciente o no existe en el destino.

**Ejemplos:**
```bash
mv archivo.txt /home/user/
mv archivo.txt archivo_viejo.txt
```

---

### 10.6 `rm` - Eliminar archivos o directorios
El comando `rm` borra archivos o directorios.

**Sintaxis:**
```bash
rm [opciones] archivo
```

**Opciones más comunes:**
- `-r`: Borra un directorio y su contenido recursivamente.
- `-i`: Pide confirmación antes de borrar cada archivo.
- `-f`: Fuerza la eliminación, sin preguntar confirmación.

**Ejemplos:**
```bash
rm archivo.txt
rm -r /home/user/carpeta
rm -rf /home/user/carpeta
```

---

### 10.7 `mkdir` - Crear un nuevo directorio
Este comando crea un nuevo directorio.

**Sintaxis:**
```bash
mkdir [opciones] directorio
```

**Opciones más comunes:**
- `-p`: Crea los directorios de manera recursiva, es decir, también crea directorios padres si no existen.

**Ejemplos:**
```bash
mkdir nuevo_directorio
mkdir -p /home/user/nueva/carpeta
```

---

### 10.8 `rmdir` - Eliminar directorios vacíos
El comando `rmdir` elimina directorios que estén vacíos.

**Sintaxis:**
```bash
rmdir [directorio]
```

**Ejemplo:**
```bash
rmdir carpeta_vacia
```

---

### 10.9 `touch` - Crear o modificar un archivo
El comando `touch` se usa para crear un archivo vacío o actualizar la fecha de modificación de un archivo existente.

**Sintaxis:**
```bash
touch archivo
```

**Ejemplo:**
```bash
touch nuevo_archivo.txt
```

---

### 10.10 `chmod` - Cambiar permisos de archivos o directorios
Este comando modifica los permisos de un archivo o directorio.

**Sintaxis:**
```bash
chmod [opciones] permisos archivo
```

**Opciones más comunes:**
- `u`: Permisos del usuario (owner).
- `g`: Permisos del grupo.
- `o`: Permisos de otros.
- `+` o `-`: Añadir o quitar permisos.

**Ejemplos:**
```bash
chmod u+x script.sh
chmod 755 archivo.txt
```

---

### 10.11 `chown` - Cambiar propietario de un archivo o directorio
El comando `chown` cambia el propietario o grupo de un archivo o directorio.

**Sintaxis:**
```bash
chown [opciones] propietario[:grupo] archivo
```

**Ejemplo:**
```bash
chown usuario:grupo archivo.txt
```

---

### 10.12 `cat` - Concatenar y mostrar archivos
El comando `cat` muestra el contenido de un archivo o lo concatena con otros.

**Sintaxis:**
```bash
cat [archivo]
```

**Ejemplos:**
```bash
cat archivo.txt
cat archivo1.txt archivo2.txt > archivo_concatenado.txt
```

---

### 10.13 `grep` - Buscar texto en archivos
El comando `grep` busca patrones dentro de archivos.

**Sintaxis:**
```bash
grep [opciones] patrón archivo
```

**Opciones más comunes:**
- `-i`: Ignorar mayúsculas y minúsculas.
- `-r`: Buscar recursivamente en directorios.
- `-n`: Muestra los números de línea donde se encuentra el patrón.

**Ejemplos:**
```bash
grep "hola" archivo.txt
grep -i "error" /var/log/syslog
grep -rn "config" /etc/
```

---

### 10.14 `df` - Mostrar el uso del disco
El comando `df` muestra el uso del espacio en disco.

**Sintaxis:**
```bash
df [opciones]
```

**Opciones más comunes:**
- `-h`: Mostrar los tamaños de manera legible.

**Ejemplo:**
```bash
df -h
```

---

### 10.15 `ps` - Mostrar procesos en ejecución
El comando `ps` muestra los procesos que están corriendo en el sistema.

**Sintaxis:**
```bash
ps [opciones]
```

**Opciones más comunes:**
- `aux`: Muestra todos los procesos en ejecución, con más detalles.

**Ejemplo:**
```bash
ps aux
```

---

## 11. Instalación y configuración del entorno

Para preparar un entorno de desarrollo se deben instalar y configurar los elementos básicos que la aplicación necesita para funcionar.

### 11.1 Requisitos mínimos

Un entorno básico suele requerir:

- sistema operativo compatible;
- navegador web;
- editor o IDE;
- software del lenguaje de programación o framework;
- servidor web o de aplicaciones;
- base de datos si la aplicación la necesita;
- permisos y rutas correctas para acceder a archivos y carpetas.

### 11.2 Configuración típica de un entorno local

Un entorno de pruebas puede consistir en:

- un editor para desarrollar el código;
- un navegador para probar la interfaz;
- un servidor local para ejecutar la aplicación;
- una base de datos local;
- un conjunto de archivos de configuración con puertos y rutas.

### 11.3 Procedimiento básico

1. Instalar el software necesario.
2. Crear la estructura del proyecto.
3. Configurar el servidor.
4. Añadir la base de datos, si procede.
5. Ejecutar la aplicación.
6. Probar la conexión a la aplicación desde el navegador.
7. Revisar errores de configuración y permisos.
8. Corregir fallos y comprobar la respuesta del sistema.

### 11.4 Buenas prácticas

- Mantener el entorno documentado.
- Usar versiones compatibles.
- Controlar permisos y rutas de acceso.
- Comprobar que la configuración es segura.
- Evitar accesos indebidos.
- Verificar errores antes de desplegar en producción.
- Proteger información sensible.
- Realizar pruebas con datos reales o similares a los reales.

---

## 12. Despliegue y explotación básica

La implantación de una aplicación web implica, además del desarrollo, su puesta en funcionamiento en un entorno que permita su uso por parte de los usuarios.

El despliegue consiste en dejar la aplicación instalada, configurada y lista para atender peticiones. En este proceso se deben considerar elementos como:

- la infraestructura disponible;
- el servidor o hosting elegido;
- la seguridad del servicio;
- la configuración del dominio o IP;
- el acceso a la base de datos;
- la gestión de logs y errores.

### Tipos de entorno de despliegue

- entorno local o de desarrollo;
- entorno de pruebas;
- entorno de producción;
- hosting compartido;
- servidor propio o VPS;
- nube pública (Azure, AWS, Google Cloud, etc.).

### Requisitos para una implantación correcta

- que el software esté instalado correctamente;
- que los puertos correspondan a la configuración;
- que la aplicación tenga permisos de acceso;
- que la base de datos esté disponible;
- que la seguridad esté habilitada;
- que el servidor responda a las peticiones de forma estable.

La explotación de la aplicación incluye también el mantenimiento, la monitorización y la revisión de errores en producción.

---

## 13. LAMP Stack en Ubuntu Server

### 13.1. Introducción

LAMP es el acrónimo usado para describir un sistema de infraestructura de Internet que usa las siguientes herramientas:

- Linux (Sistema Operativo)
- Apache (Servidor Web)
- MySQL/MariaDB (Sistema Gestor de Bases de Datos)
- PHP (Lenguaje de programación)

En esta práctica vamos a utilizar el sistema operativo Ubuntu Server.

---

## 13.2. Linux

### 13.2.1. Primeros pasos con `apt`

`apt` (Advanced Packaging Tool) es el sistema gestor de paquetes utilizado en distribuciones Debian y sus derivadas, como Ubuntu.

#### 13.2.1.1. `apt update`

Actualiza la lista de paquetes:

```bash
sudo apt update
```

#### 13.2.1.2. `apt upgrade`

Actualiza los paquetes instalados a sus últimas versiones disponibles. Los paquetes relacionados con el kernel no se actualizarán. Tampoco se resolverán los problemas de dependencias que necesiten eliminar otros paquetes.

```bash
sudo apt upgrade
```

#### 13.2.1.3. `apt full-upgrade`

Realiza una actualización más completa del sistema operativo, como la actualización del kernel, la resolución de dependencias entre paquetes, la instalación y eliminación de paquetes si fuese necesario, etc. También permite actualizar la versión del sistema operativo.

```bash
sudo apt full-upgrade
```

#### 13.2.1.4. `apt install`

Instala un paquete determinado:

```bash
sudo apt install <package-name>
```

#### 13.2.1.5. `apt remove`

Desinstala un paquete:

```bash
sudo apt remove <package-name>
```

#### 13.2.1.6. `apt purge`

Desinstala un paquete determinado y elimina los archivos de configuración asociados:

```bash
sudo apt purge <package-name>
```

#### 13.2.1.7. `apt search`

Busca un paquete entre las descripciones de los paquetes:

```bash
sudo apt search <package-name>
```

#### 13.2.1.8. `apt show`

Muestra los detalles de un paquete:

```bash
sudo apt show <package-name>
```

### 13.2.2. Instalación de un GUI Desktop

Ubuntu Server no cuenta con una interfaz gráfica de usuario (GUI) por defecto, pero si fuese necesario podemos instalar un GUI Desktop.

```bash
sudo apt install ubuntu-desktop
```

```bash
sudo apt install ubuntu-gnome-desktop
```

```bash
sudo apt install kubuntu-desktop
```

Otros escritorios que podemos instalar son: `xubuntu-desktop`, `lubuntu-desktop`, `edubuntu-desktop`, etc.

### 13.2.3. Instalación de un servidor SSH

Ubuntu Server ya cuenta con un servidor SSH instalado por defecto, pero si fuese necesario instalarlo podemos hacerlo con el siguiente comando:

```bash
sudo apt install ssh -y
```

### 13.2.4. Cómo iniciar, parar y consultar el servicio de SSH

#### 13.2.4.1. Método 1: `systemctl`

La mayoría de distribuciones Linux modernas utilizan `systemd` como sistema de inicio y administrador de servicios predeterminado.

```bash
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl status ssh
```

#### 13.2.4.2. Método 2: `/etc/init.d/`

Algunas distribuciones Linux más antiguas pueden seguir utilizando `SysVinit`.

```bash
sudo /etc/init.d/ssh start
sudo /etc/init.d/ssh stop
sudo /etc/init.d/ssh status
```

### 13.2.5. Instalación de `git`

Ubuntu Server tiene instalado por defecto el sistema de control de versiones `git`, pero si fuese necesario instalarlo podemos hacerlo con el siguiente comando:

```bash
sudo apt install git -y
```

---

## 13.3. Apache

### 13.3.1. Instalación de Apache

```bash
sudo apt install apache2 -y
```

### 13.3.2. Cómo iniciar, parar y consultar el estado de Apache

#### 13.3.2.1. Método 1: `systemctl`

```bash
sudo systemctl start apache2
sudo systemctl stop apache2
sudo systemctl restart apache2
sudo systemctl reload apache2
sudo systemctl status apache2
```

#### 13.3.2.2. Método 2: `/etc/init.d/`

```bash
sudo /etc/init.d/apache2 start
sudo /etc/init.d/apache2 stop
sudo /etc/init.d/apache2 restart
sudo /etc/init.d/apache2 reload
sudo /etc/init.d/apache2 status
```

#### 13.3.2.3. Método 3: `service`

```bash
sudo service apache2 start
sudo service apache2 stop
sudo service apache2 restart
sudo service apache2 reload
sudo service apache2 status
```

### 13.3.3. Archivos de configuración de Apache

Los archivos de configuración de Apache se almacenan en el directorio:

```bash
/etc/apache2/
```

Dentro de este directorio encontramos los siguientes archivos y directorios:

```text
/etc/apache2/
├── apache2.conf
├── envvars
├── magic
├── ports.conf
├── conf-available/
├── conf-enabled/
├── mods-available/
├── mods-enabled/
├── sites-available/
└── sites-enabled/
```

**Descripción breve:**

- `apache2.conf`: archivo de configuración principal; incluye el resto de archivos.
- `envvars`: variables de entorno para Apache.
- `magic`: instrucciones para determinar el tipo MIME de un archivo.
- `ports.conf`: puertos TCP donde Apache escucha peticiones.
- `conf-available`: archivos de configuración globales para todos los hosts virtuales.
- `conf-enabled`: enlaces simbólicos hacia los archivos activos.
- `mods-available`: módulos disponibles.
- `mods-enabled`: módulos activos.
- `sites-available`: archivos de configuración de hosts virtuales.
- `sites-enabled`: hosts virtuales activos.

### 13.3.4. Cómo modificar el puerto por defecto de Apache

Para configurar los puertos donde Apache escuchará las peticiones HTTP, hay que modificar el archivo `/etc/apache2/ports.conf`.

Contenido por defecto del archivo:

```apacheconf
# If you just change the port or add more ports here, you will likely also
# have to change the VirtualHost statement in
# /etc/apache2/sites-enabled/000-default.conf

Listen 80

<IfModule ssl_module>
   Listen 443
</IfModule>

<IfModule mod_gnutls.c>
   Listen 443
</IfModule>
```

Ejemplo: modificar el puerto por defecto a `8000`.

```apacheconf
Listen 8000

<IfModule ssl_module>
   Listen 443
</IfModule>

<IfModule mod_gnutls.c>
   Listen 443
</IfModule>
```

Una vez modificado el archivo, también hay que cambiar el puerto en el host virtual por defecto:

```apacheconf
<VirtualHost *:8000>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /var/www/html
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Después, reiniciamos Apache:

```bash
sudo systemctl restart apache2
```

> No olvidar comprobar que el nuevo puerto está abierto en el firewall.

### 13.3.5. Cómo modificar el directorio por defecto de Apache

El directorio que utiliza Apache para servir contenido se configura con la directiva `DocumentRoot`, que por defecto vale `/var/www/html`.

Ejemplo de configuración del archivo `/etc/apache2/sites-available/000-default.conf`:

```apacheconf
<VirtualHost *:80>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /var/www/html
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Ejemplo: cambiar el directorio a `/home/ubuntu/misitioweb`.

```bash
mkdir -p /home/ubuntu/misitioweb
echo "Hola mundo!" > /home/ubuntu/misitioweb/index.html
sudo chown -R www-data:www-data /home/ubuntu/misitioweb
sudo chmod 755 /home/ubuntu
sudo chmod 755 /home/ubuntu/misitioweb
```

Configuración del sitio virtual:

```apacheconf
<VirtualHost *:80>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /home/ubuntu/misitioweb

   <Directory /home/ubuntu/misitioweb>
      Options Indexes FollowSymLinks
      AllowOverride None
      Require all granted
   </Directory>

   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

**Opciones del bloque `<Directory>`**:

- `Options Indexes FollowSymLinks`: permite listar directorios y seguir enlaces simbólicos.
- `AllowOverride None`: no permite archivos `.htaccess`.
- `Require all granted`: permite el acceso a todos los usuarios.

Después, reiniciamos Apache:

```bash
sudo systemctl restart apache2
```

### 13.3.6. Cómo habilitar o deshabilitar un módulo de Apache

Para habilitar un módulo de Apache se utiliza `a2enmod`.

Ejemplo: activar el módulo `rewrite`.

```bash
sudo a2enmod rewrite
sudo systemctl restart apache2
```

Para deshabilitar un módulo se usa `a2dismod`.

```bash
sudo a2dismod rewrite
sudo systemctl restart apache2
```

### 13.3.7. Cómo configurar la directiva `DirectoryIndex`

La directiva `DirectoryIndex` se utiliza para configurar el orden de prioridad con el que se muestran los archivos cuando se accede a un directorio.

Ejemplo:

```apacheconf
DirectoryIndex index.php index.html
```

Si la configuración fuese la anterior, el servidor enviaría `index.php` antes que `index.html`.

Se puede configurar a nivel global en `/etc/apache2/mods-available/dir.conf` o dentro de cada host virtual.

Ejemplo en `/etc/apache2/mods-available/dir.conf`:

```apacheconf
DirectoryIndex index.php index.html index.cgi index.pl index.php index.xhtml index.htm
```

Ejemplo en un host virtual:

```apacheconf
<VirtualHost *:80>
   ServerAdmin webmaster@localhost
   DocumentRoot /var/www/html/
   DirectoryIndex index.php index.html
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

### 13.3.8. Cómo crear un nuevo host virtual

Los hosts virtuales se crean en `/etc/apache2/sites-available/`.

Para habilitarlos y deshabilitarlos se usan:

```bash
sudo a2ensite <nombre_del_archivo_de_configuración>
sudo a2dissite <nombre_del_archivo_de_configuración>
```

#### 13.3.8.1. Host virtual basado en el nombre de dominio

**Paso 1**: crear directorios para cada sitio.

```bash
sudo mkdir -p /var/www/html/web1
sudo mkdir -p /var/www/html/web2
sudo chown -R www-data:www-data /var/www/html
```

**Paso 2**: crear un archivo `index.html` para cada sitio.

```bash
echo "Sitio web 1" | sudo tee /var/www/html/web1/index.html
echo "Sitio web 2" | sudo tee /var/www/html/web2/index.html
```

**Paso 3**: crear los archivos de configuración.

```bash
sudo nano /etc/apache2/sites-available/web1.conf
```

```apacheconf
<VirtualHost *:80>
   ServerAdmin webmaster@web1.com
   ServerName web1.com
   DocumentRoot /var/www/html/web1
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

```bash
sudo nano /etc/apache2/sites-available/web2.conf
```

```apacheconf
<VirtualHost *:80>
   ServerAdmin webmaster@web2.com
   ServerName web2.com
   DocumentRoot /var/www/html/web2
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

**Paso 4**: deshabilitar el sitio por defecto y activar los nuevos hosts.

```bash
sudo a2dissite 000-default.conf
sudo a2ensite web1.conf
sudo a2ensite web2.conf
```

**Paso 5**: recargar Apache.

```bash
sudo systemctl reload apache2
```

**Paso 6**: comprobar los sitios virtuales.

Hay dos opciones:

1. Registrar los dominios en un proveedor DNS para que apunten a la IP pública del servidor.
2. Editar el archivo `/etc/hosts` del equipo para resolver nombres locales.

Ejemplo:

```text
IP_SERVIDOR_WEB web1.com
IP_SERVIDOR_WEB web2.com
```

Si la IP pública del servidor es `172.16.12.178`, quedaría así:

```text
172.16.12.178 web1.com
172.16.12.178 web2.com
```

#### 13.3.8.2. Host virtual basado en el puerto

Es posible crear sitios virtuales que escuchen en puertos distintos y sirvan contenido según el puerto solicitado.

Ejemplo:

```apacheconf
Listen 8000
<VirtualHost *:8000>
   DocumentRoot /var/www/html/web-port-8000
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

Listen 80
<VirtualHost *:80>
   DocumentRoot /var/www/html/web-port-80
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

### 13.3.9. Cómo consultar los hosts virtuales activos

```bash
sudo apache2ctl -S
```

También se puede listar el contenido del directorio:

```bash
ls -l /etc/apache2/sites-enabled/
```

### 13.3.10. Cómo comprobar la sintaxis de los archivos de configuración de Apache

```bash
sudo apache2ctl configtest
```

### 13.3.11. Cómo ocultar la versión de Apache al cliente

Por razones de seguridad y privacidad, se considera una buena práctica ocultar la versión del servidor web al cliente.

Las directivas relevantes son:

- `ServerSignature`: incluye la versión del servidor en páginas de error e índices de directorio.
- `ServerTokens`: controla el nivel de detalle de la información del servidor que se incluye en las respuestas HTTP.

> `ServerTokens` debe aplicarse a todo el servidor; `ServerSignature` puede configurarse por host virtual.

Ejemplo:

```apacheconf
ServerSignature Off
ServerTokens Prod
```

Ejemplo en el sitio virtual por defecto:

```apacheconf
ServerSignature Off
ServerTokens Prod

<VirtualHost *:80>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /home/ubuntu/misitioweb

   <Directory /home/ubuntu/misitioweb>
      Options Indexes FollowSymLinks
      AllowOverride None
      Require all granted
   </Directory>

   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Para comprobar las cabeceras HTTP enviadas al cliente:

```bash
curl -Iv http://IP_SERVIDOR_WEB
```

El parámetro `-I` muestra solo las cabeceras HTTP y `-v` muestra salida detallada.

### 13.3.12. Archivos de log de Apache

Los archivos de log de Apache suelen almacenarse en `/var/log/apache2/`.

#### 13.3.12.1. `access.log`

Este archivo almacena datos de acceso de todas las peticiones que procesa. Podemos hacer un seguimiento con:

```bash
tail -f /var/log/apache2/access.log
```

#### 13.3.12.2. `error.log`

Este archivo contiene el registro de errores del servidor.

```bash
tail -f /var/log/apache2/error.log
```

#### 13.3.12.3. Mensajes de error más detallados en Apache

Para localizar errores con más detalle, debemos configurar la línea `LogLevel` en `/etc/apache2/apache2.conf`.

```apacheconf
LogLevel debug
```

Los niveles disponibles son, de mayor a menor importancia:

- `emerg`: emergencias; el servidor no se puede utilizar.
- `alert`: requiere intervención inmediata.
- `crit`: condiciones críticas.
- `error`: condiciones de error.
- `warn`: advertencias.
- `notice`: condiciones normales pero significativas.
- `info`: mensajes informativos.
- `debug`: información detallada de depuración.

> `emerg` registra menos información y `debug` mucho más. Conviene usar `debug` solo para diagnosticar problemas concretos.

---

## 13.4. MySQL Server

### 13.4.1. Instalación de MySQL Server

```bash
sudo apt install mysql-server -y
```

### 13.4.2. Cómo iniciar, parar y consultar el estado de MySQL Server

#### 13.4.2.1. Método 1: `systemctl`

```bash
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

#### 13.4.2.2. Método 2: `/etc/init.d/`

```bash
sudo /etc/init.d/mysql start
sudo /etc/init.d/mysql stop
sudo /etc/init.d/mysql restart
sudo /etc/init.d/mysql reload
sudo /etc/init.d/mysql force-reload
sudo /etc/init.d/mysql status
```

### 13.4.3. Archivos de configuración de MySQL Server

```bash
/etc/mysql/mysql.cnf
```

También podemos encontrar archivos de configuración en:

```bash
/etc/mysql/conf.d/
/etc/mysql/mysql.conf.d/
```

### 13.4.4. Archivos de log de MySQL Server

```bash
/var/log/mysql/error.log
```

### 13.4.5. Cómo acceder a MySQL Server desde consola con el usuario `root`

#### Opción 1

En primer lugar iniciamos sesión como `root`:

```bash
sudo su
```

Después entramos en la consola de MySQL como `root`:

```bash
mysql -u root
```

#### Opción 2

```bash
sudo mysql
```

### 13.4.6. Cómo cambiar la contraseña del usuario `root` (Método 1)

Primero accedemos a la consola de MySQL y seleccionamos la base de datos `mysql`:

```sql
USE mysql;
SELECT User, Host, plugin FROM user;
```

Salida típica:

```text
+------------------+-----------+-----------------------+
| User             | Host      | plugin                |
+------------------+-----------+-----------------------+
| root             | localhost | auth_socket           |
| mysql.session    | localhost | caching_sha2_password |
| mysql.sys       | localhost | caching_sha2_password |
| debian-sys-maint | localhost | caching_sha2_password |
+------------------+-----------+-----------------------+
```

Si queremos cambiar la contraseña de `root`, hay que cambiar el método de autenticación a `mysql_native_password` o `caching_sha2_password`.

**Opción `mysql_native_password` (antigua):**

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'nueva_contraseña';
```

**Opción `caching_sha2_password` (nueva):**

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'nueva_contraseña';
```

Después se debe aplicar la actualización:

```sql
FLUSH PRIVILEGES;
```

### 13.4.7. Cómo cambiar la contraseña del usuario `root` (Método 2: `--skip-grant-tables`)

Otra opción es iniciar MySQL con `--skip-grant-tables`, lo que permite conectarse sin autenticación.

**Paso 1**: detener MySQL.

```bash
sudo systemctl stop mysql
```

**Paso 2**: crear el directorio `/var/run/mysqld` si no existe.

```bash
sudo mkdir -p /var/run/mysqld
sudo chown mysql:mysql /var/run/mysqld
```

**Paso 3**: arrancar `mysqld` en segundo plano con la opción `--skip-grant-tables`.

```bash
sudo /usr/sbin/mysqld --skip-grant-tables &
```

**Paso 4**: comprobar que el proceso está ejecutándose.

```bash
ps aux | grep mysqld
```

**Paso 5**: entrar sin usuario ni contraseña.

```bash
mysql
```

**Paso 6**: recargar privilegios y cambiar la contraseña.

```sql
FLUSH PRIVILEGES;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'nueva_contraseña';
```

**Paso 7**: salir y reiniciar el servicio.

```bash
exit
sudo pkill mysqld
sudo systemctl start mysql
```

### 13.4.8. Algunos comandos útiles para MySQL desde consola

#### 13.4.8.1. Listar todas las bases de datos disponibles

```sql
SHOW DATABASES;
```

#### 13.4.8.2. Crear una nueva base de datos

```sql
CREATE DATABASE <database>;
```

#### 13.4.8.3. Borrar una base de datos

```sql
DROP DATABASE <database>;
```

#### 13.4.8.4. Seleccionar una base de datos

```sql
USE <database>;
```

#### 13.4.8.5. Listar las tablas de una base de datos

```sql
SHOW TABLES;
```

#### 13.4.8.6. Mostrar la estructura de una tabla

```sql
DESCRIBE <table>;
```

#### 13.4.8.7. Cerrar la sesión y salir

```sql
exit
quit
```

### 13.4.9. Usuarios y permisos en MySQL desde consola

#### 13.4.9.1. Eliminar un usuario

```sql
DROP USER [IF EXISTS] user [, user] ...
```

Ejemplo:

```sql
DROP USER IF EXISTS 'nombre_usuario'@'localhost';
```

#### 13.4.9.2. Crear un nuevo usuario

Sintaxis simplificada:

```sql
CREATE USER [IF NOT EXISTS]
user [auth_option] [, user [auth_option]] ...
DEFAULT ROLE role [, role ] ...
[REQUIRE {NONE | tls_option [[AND] tls_option] ...}]
[WITH resource_option [resource_option] ...]
[password_option | lock_option] ...
[COMMENT 'comment_string' | ATTRIBUTE 'json_object']
```

Ejemplo:

```sql
CREATE USER 'nombre_usuario'@'localhost' IDENTIFIED BY 'contraseña';
```

#### 13.4.9.3. Tipos de permisos que podemos aplicar

- `ALL PRIVILEGES`: acceso a todas las bases de datos asignadas.
- `CREATE`: crear tablas o bases de datos.
- `DROP`: eliminar tablas o bases de datos.
- `DELETE`: eliminar registros.
- `INSERT`: insertar registros.
- `SELECT`: leer registros.
- `UPDATE`: actualizar registros.
- `GRANT OPTION`: asignar privilegios a otros usuarios.

#### 13.4.9.4. Asignar permisos a un usuario

```sql
GRANT [permiso] ON [nombre_base_de_datos].[nombre_tabla] TO 'nombre_usuario'@'localhost';
```

Ejemplo:

```sql
GRANT ALL PRIVILEGES ON *.* TO 'nombre_usuario'@'localhost';
FLUSH PRIVILEGES;
```

#### 13.4.9.5. Eliminar permisos a un usuario

```sql
REVOKE [permiso] ON [nombre_base_de_datos].[nombre_tabla] FROM 'nombre_usuario'@'localhost';
```

#### 13.4.9.6. Consultar los usuarios creados en MySQL

Los usuarios de MySQL se almacenan en la tabla `mysql.user`.

```sql
SELECT user, host FROM mysql.user;
```

Ejemplo de salida:

```text
+------------------+--------------+
| user             | host         |
+------------------+--------------+
| root             | localhost    |
| debian-sys-maint | localhost    |
| mysql.session    | localhost    |
| mysql.sys       | localhost    |
+------------------+--------------+
```

También podemos consultar los permisos específicos de un usuario:

```sql
SHOW GRANTS FOR root@localhost;
```

```text
+---------------------------------------------------+
| Grants for root@localhost                         |
+---------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' |
+---------------------------------------------------+
```

### 13.4.10. Cómo ejecutar un script `.sql` desde la consola

**Desde la consola de Linux:**

```bash
mysql -u root -p < script.sql
```

**Desde la consola de MySQL:**

```sql
mysql> source script.sql
```

### 13.4.11. Cómo ejecutar sentencias SQL desde un script de bash

#### Opción 1: redirección

```bash
mysql -u $DB_USER -p$DB_PASSWORD $DB_NAME < script.sql
```

Variables:

- `$DB_USER`: usuario de la base de datos.
- `$DB_PASSWORD`: contraseña del usuario.
- `$DB_NAME`: nombre de la base de datos.
- `script.sql`: archivo con las instrucciones SQL.

#### Opción 2: parámetro `-e`

```bash
mysql -u $DB_USER -p$DB_PASSWORD $DB_NAME -e "SELECT * FROM tabla;"
```

#### Opción 3: operador `<<<`

```bash
#!/bin/bash

DB_USER=usuario
DB_PASSWORD=contraseña
DB_NAME=base_de_datos

mysql -u root <<< "DROP USER IF EXISTS '$DB_USER'@'%'"
mysql -u root <<< "CREATE USER '$DB_USER'@'%' IDENTIFIED BY '$DB_PASSWORD'"
mysql -u root <<< "GRANT ALL PRIVILEGES ON $DB_NAME.* TO '$DB_USER'@'%'"
```

---

## 13.5. PHP

### 13.5.1. ¿Qué es PHP?

PHP es un lenguaje de programación de uso general, especialmente adecuado para el desarrollo web.

El código PHP puede ser interpretado y ejecutado desde la interfaz de línea de comandos (CLI) o desde un servidor web con intérprete PHP.

### 13.5.2. ¿Cómo funciona PHP?

PHP se ejecuta en el servidor. Cuando el navegador solicita una página PHP, el servidor procesa el código y devuelve el resultado al cliente, normalmente en formato HTML.

### 13.5.3. Instalación de módulos PHP

Para que Apache pueda procesar código PHP, necesitamos instalar el intérprete de PHP y algunos módulos adicionales.

Paquetes recomendados:

- `php`: intérprete de PHP.
- `libapache2-mod-php`: permite servir páginas PHP desde Apache.
- `php-mysql`: permite conectar a MySQL desde PHP.

```bash
sudo apt install php libapache2-mod-php php-mysql -y
```

Después de la instalación, reiniciamos Apache.

```bash
sudo systemctl restart apache2
```

Dependiendo de la aplicación, puede ser necesario instalar módulos adicionales. Para consultar detalles del paquete, se puede usar:

```bash
sudo apt show libapache2-mod-php
```

### 13.5.4. Comprobar que la instalación se ha realizado correctamente

Crea un archivo llamado `info.php` en `/var/www/html`:

```bash
sudo nano /var/www/html/info.php
```

Contenido:

```php
<?php
phpinfo();
?>
```

Accede desde un navegador con la URL:

```text
http://IP/info.php
```

Por ejemplo, si la IP es `192.168.22.200`: 

```text
http://192.168.22.200/info.php
```

---

## 13.6. Otras herramientas relacionadas con la pila LAMP

### 13.6.1. Instalar phpMyAdmin para acceder vía web a MySQL

#### 13.6.1.1. Instalación con `apt`

**Paso 1**: instalar los paquetes necesarios.

```bash
sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl -y
```

Descripción de algunos paquetes:

- `php-mbstring`: permite manejar cadenas multibyte.
- `php-zip`: permite trabajar con archivos `.zip`.
- `php-gd`: librería para crear y manipular imágenes.
- `php-json`: soporte para JSON en PHP.
- `php-curl`: interacción con servidores mediante diferentes protocolos.

**Paso 2**: durante la instalación, se pedirá seleccionar el servidor web a configurar. En este caso se selecciona `apache2`.

**Paso 3**: confirmar el uso de `dbconfig-common` para configurar la base de datos.

**Paso 4**: introducir la contraseña para phpMyAdmin.

Una vez finalizada la instalación, puede accederse a la interfaz web con:

```text
http://IP/phpmyadmin
```

Ejemplo:

```text
http://192.168.22.200/phpmyadmin
```

**Automatización con Bash**:

```bash
echo "phpmyadmin phpmyadmin/reconfigure-webserver multiselect apache2" | debconf-set-selections
echo "phpmyadmin phpmyadmin/dbconfig-install boolean true" | debconf-set-selections
echo "phpmyadmin phpmyadmin/mysql/app-pass password $PHPMYADMIN_APP_PASSWORD" | debconf-set-selections
echo "phpmyadmin phpmyadmin/app-password-confirm password $PHPMYADMIN_APP_PASSWORD" | debconf-set-selections
```

#### 13.6.1.2. Otros métodos para instalar phpMyAdmin

En la documentación oficial de phpMyAdmin se pueden consultar otras posibilidades:

- Instalación desde Git.
- Instalación usando Composer.
- Instalación usando Docker.
- Instalación rápida.

### 13.6.2. Instalar Adminer para acceder vía web a MySQL

Adminer es una alternativa a phpMyAdmin. Tiene la ventaja de distribuirse en un único archivo `.php`.

```bash
mkdir -p /var/www/html/adminer
wget https://github.com/vrana/adminer/releases/download/v4.8.1/adminer-4.8.1-mysql.php -P /var/www/html/adminer
```

### 13.6.3. Instalar un analizador de logs para Apache Server

Existen varios analizadores de logs para Apache, como `GoAccess` o `AWStats`.

#### 13.6.3.1. GoAccess

Para instalar la última versión de GoAccess introducimos sus repositorios oficiales.

```bash
sudo apt update
sudo apt install goaccess -y
```

#### 13.6.3.2. Uso de GoAccess

##### Desde el terminal

```bash
goaccess /var/log/apache2/access.log -c
```

Este comando analiza el archivo `access.log` y muestra información del log en tiempo real en el terminal.

##### Creación de un archivo HTML estático

```bash
goaccess /var/log/apache2/access.log -o /var/www/html/report.html --log-format=COMBINED
```

##### Creación de un archivo HTML en tiempo real

```bash
goaccess /var/log/apache2/access.log -o /var/www/html/report.html --log-format=COMBINED --real-time-html
```

> Si se genera HTML en tiempo real, hay que abrir el puerto `7890` en el firewall porque es el que usa el WebSocket del cliente JavaScript.

#### 13.6.3.3. Creación de un archivo HTML en tiempo real en segundo plano

```bash
goaccess /var/log/apache2/access.log -o /var/www/html/report.html --log-format=COMBINED --real-time-html --daemonize
```

### 13.6.4. Control de acceso a un directorio con autenticación básica

Crea un directorio `stats` dentro de `/var/www/html` para consultar informes generados con GoAccess. El acceso debe estar protegido con usuario y contraseña.

**Paso 1**: crear el directorio.

```bash
mkdir -p /var/www/html/stats
```

**Paso 2**: ejecutar GoAccess en segundo plano.

```bash
goaccess /var/log/apache2/access.log -o /var/www/html/stats/index.html --log-format=COMBINED --daemonize
```

También se puede usar `nohup`, `screen` o `tmux` para evitar que el proceso termine al cerrar la sesión SSH.

Ejemplo con `nohup`:

```bash
nohup goaccess /var/log/apache2/access.log -o /var/www/html/stats/index.html --log-format=COMBINED --real-time-html &
```

Ejemplo con `screen`:

```bash
screen -dmL goaccess /var/log/apache2/access.log -o /var/www/html/stats/index.html --log-format=COMBINED --real-time-html
```

**Paso 3**: crear archivo de contraseñas.

```bash
sudo htpasswd -c /etc/apache2/.htpasswd usuario
```

Si se quiere automatizar en un script, se puede usar la opción `-b`:

```bash
sudo htpasswd -bc /etc/apache2/.htpasswd $STATS_USERNAME $STATS_PASSWORD
```

**Paso 4**: editar la configuración de Apache.

```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```

Añadir la siguiente sección dentro de `<VirtualHost *:80>`:

```apacheconf
<Directory "/var/www/html/stats">
   AuthType Basic
   AuthName "Acceso restringido"
   AuthBasicProvider file
   AuthUserFile "/etc/apache2/.htpasswd"
   Require valid-user
</Directory>
```

Ejemplo completo:

```apacheconf
<VirtualHost *:80>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /var/www/html

   <Directory "/var/www/html/stats">
      AuthType Basic
      AuthName "Acceso restringido"
      AuthBasicProvider file
      AuthUserFile "/etc/apache2/.htpasswd"
      Require valid-user
   </Directory>

   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

**Qué significa cada directiva**:

- `AuthType Basic`: indica autenticación básica.
- `AuthName`: texto que mostrará el navegador al usuario.
- `AuthBasicProvider file`: usa un archivo como proveedor de autenticación.
- `AuthUserFile`: ruta al archivo `.htpasswd`.
- `Require valid-user`: permite acceso a cualquier usuario del archivo.

**Paso 5**: reiniciar Apache.

```bash
sudo systemctl restart apache2
```

### 13.6.5. Control de acceso a un directorio con `.htaccess`

Los archivos `.htaccess` permiten realizar cambios de configuración en un directorio concreto sin modificar el archivo principal de Apache.

**Paso 1**: crear el directorio.

```bash
mkdir -p /var/www/html/stats
```

**Paso 2**: lanzar GoAccess en segundo plano.

```bash
sudo goaccess /var/log/apache2/access.log -o /var/www/html/stats/index.html --log-format=COMBINED --real-time-html &
```

**Paso 3**: crear el archivo de contraseñas.

```bash
sudo htpasswd -c /etc/apache2/.htpasswd usuario
```

O con parámetros automáticos:

```bash
sudo htpasswd -bc /etc/apache2/.htpasswd $STATS_USERNAME $STATS_PASSWORD
```

**Paso 4**: crear el archivo `.htaccess` dentro del directorio a proteger.

```bash
sudo nano /var/www/html/stats/.htaccess
```

Contenido:

```apacheconf
AuthType Basic
AuthName "Acceso restringido"
AuthBasicProvider file
AuthUserFile "/etc/apache2/.htpasswd"
Require valid-user
```

Las directivas son las mismas que en la autenticación básica usando `<Directory>`, con la diferencia de que aquí se aplican directamente a ese directorio.

**Paso 5**: permitir sobrescritura en el directorio desde Apache.

```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```

Dentro del bloque `VirtualHost`:

```apacheconf
<Directory "/var/www/html/stats">
   AllowOverride All
</Directory>
```

Ejemplo completo:

```apacheconf
<VirtualHost *:80>
   #ServerName www.example.com
   ServerAdmin webmaster@localhost
   DocumentRoot /var/www/html

   <Directory "/var/www/html/stats">
      AllowOverride All
   </Directory>

   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

**Paso 6**: reiniciar Apache.

```bash
sudo systemctl restart apache2
```

---

## 14. Proyecto final: instalación y documentación de una pila LAMP

### 14.1. Descripción de la actividad

En este proyecto final se instalará y configurará una pila **LAMP** en un servidor Ubuntu. LAMP está formada por Linux, Apache, MySQL/MariaDB y PHP.

El proyecto se realizará en grupos, pero **todo el alumnado deberá instalar y comprobar el funcionamiento de todos los componentes de la pila LAMP** en su propia máquina virtual o servidor. El reparto por grupos determina la parte sobre la que cada grupo deberá elaborar una guía técnica completa y realizar la exposición en clase.

### 14.2. Objetivos

- Instalar y administrar una pila LAMP en Ubuntu Server.
- Verificar el funcionamiento de Apache, MySQL/MariaDB y PHP.
- Consultar registros, identificar errores y aplicar soluciones.
- Elaborar documentación técnica clara, ordenada y reproducible.
- Explicar el proceso técnico realizado ante el resto de la clase.
- Trabajar de forma coordinada en un equipo.

### 14.3. Organización de los grupos

La clase se organizará en tres grupos de trabajo:

| Grupo | Parte asignada | Responsabilidad principal |
| --- | --- | --- |
| **Grupo 1** | Apache | Instalación, configuración y comprobación del servidor web Apache. |
| **Grupo 2** | MySQL/MariaDB | Instalación, administración básica y comprobación del servidor de bases de datos. |
| **Grupo 3** | PHP | Instalación de PHP, módulos necesarios e integración con Apache y MySQL/MariaDB. |

> Todos los grupos deben instalar la pila LAMP completa. Cada grupo se especializará en su componente asignado para documentarlo y exponerlo.

### 14.4. Requisitos comunes para todo el alumnado

Cada estudiante deberá realizar en su entorno los siguientes requisitos mínimos:

1. Disponer de una instalación funcional de Ubuntu Server.
2. Actualizar los repositorios y paquetes del sistema.
3. Instalar Apache, MySQL/MariaDB y PHP.
4. Comprobar que los servicios necesarios están activos.
5. Verificar el acceso al servidor web desde un navegador.
6. Comprobar que PHP se procesa correctamente mediante un archivo de prueba.
7. Comprobar la conexión entre PHP y MySQL/MariaDB mediante una prueba funcional.
8. Conservar evidencias del proceso: comandos utilizados, capturas de pantalla, mensajes de error y soluciones aplicadas.

La instalación deberá poder verificarse, como mínimo, con las siguientes comprobaciones:

```bash
sudo systemctl status apache2
sudo systemctl status mysql
php --version
```

Además, deberá mostrarse una página PHP funcional desde Apache y una prueba de conexión a la base de datos.

### 14.5. Trabajo específico de cada grupo

#### 14.5.1. Grupo 1: Apache

El Grupo 1 deberá elaborar una guía técnica completa sobre Apache que incluya, como mínimo:

- Instalación del paquete `apache2`.
- Inicio, parada, reinicio, recarga y consulta del estado del servicio.
- Ubicación y función de los principales archivos y directorios de configuración.
- Configuración del puerto de escucha.
- Configuración del directorio raíz del sitio mediante `DocumentRoot`.
- Creación y activación de un host virtual.
- Consulta de hosts virtuales activos y validación de la sintaxis de configuración.
- Consulta de los archivos `access.log` y `error.log`.
- Pruebas de funcionamiento desde el navegador y desde la terminal.

#### 14.5.2. Grupo 2: MySQL/MariaDB

El Grupo 2 deberá elaborar una guía técnica completa sobre MySQL/MariaDB que incluya, como mínimo:

- Instalación del servidor de bases de datos.
- Inicio, parada, reinicio y consulta del estado del servicio.
- Acceso a la consola con el usuario administrador.
- Creación de una base de datos.
- Creación de un usuario con contraseña.
- Asignación y retirada de permisos sobre una base de datos.
- Creación de una tabla e inserción de datos de prueba.
- Consulta de datos desde la consola SQL.
- Ubicación de archivos de configuración y registros de errores.
- Medidas básicas de seguridad aplicadas durante la configuración.

#### 14.5.3. Grupo 3: PHP

El Grupo 3 deberá elaborar una guía técnica completa sobre PHP que incluya, como mínimo:

- Instalación de PHP y del módulo de integración con Apache.
- Instalación del módulo de conexión con MySQL/MariaDB.
- Consulta de la versión instalada y de los módulos disponibles.
- Creación de un archivo `info.php` para comprobar el procesamiento de PHP.
- Creación de una página PHP de prueba.
- Creación de un script PHP que se conecte a MySQL/MariaDB y consulte datos.
- Identificación de los archivos de configuración principales de PHP.
- Reinicio de Apache después de modificar la configuración necesaria.
- Comprobación de errores habituales de PHP y revisión de sus registros.

### 14.6. Entregable: guía técnica del grupo

Cada grupo entregará una guía siguiendo la plantilla proporcionada por el profesorado. La guía deberá ser completa, clara y permitir que otra persona reproduzca el proceso sin ayuda adicional.

La guía deberá incluir los siguientes apartados:

1. **Portada**: título del trabajo, componente asignado, integrantes del grupo y fecha.
2. **Índice**: relación de los apartados del documento.
3. **Objetivo de la guía**: qué componente se instala y qué se pretende conseguir.
4. **Requisitos previos**: sistema operativo, permisos necesarios, red, paquetes previos y cualquier condición necesaria.
5. **Proceso de instalación**: pasos ordenados, explicados y acompañados de los comandos utilizados.
6. **Configuración**: archivos modificados, directivas relevantes y explicación de los cambios.
7. **Comprobaciones**: pruebas realizadas para confirmar que la instalación funciona correctamente.
8. **Errores encontrados**: mensajes de error, causa identificada y contexto en el que se produjo cada problema.
9. **Soluciones aplicadas**: procedimiento seguido para resolver cada error y resultado obtenido.
10. **Buenas prácticas y seguridad**: recomendaciones relacionadas con el componente documentado.
11. **Conclusiones**: valoración del trabajo realizado y aprendizajes obtenidos.
12. **Referencias**: documentación oficial, recursos técnicos y fuentes consultadas.

Los comandos deberán mostrarse en bloques de código e indicar claramente cuándo deben ejecutarse como usuario normal y cuándo con `sudo`.

```bash
sudo apt update
sudo apt install apache2 -y
sudo systemctl status apache2
```

Los archivos de configuración deberán documentarse con su ruta y con bloques de código adecuados:

```apacheconf
<VirtualHost *:80>
   ServerName ejemplo.local
   DocumentRoot /var/www/ejemplo
</VirtualHost>
```

### 14.7. Exposición en clase

Cada grupo realizará una exposición oral en clase sobre la parte asignada. La presentación deberá incluir una demostración práctica siempre que sea posible.

La exposición deberá explicar:

- Qué componente se ha instalado y cuál es su función dentro de LAMP.
- Qué requisitos previos eran necesarios.
- Cuáles han sido los pasos principales de instalación y configuración.
- Qué archivos, servicios y comandos son más importantes.
- Qué comprobaciones se han realizado para validar la instalación.
- Qué errores se han encontrado y cómo se han resuelto.
- Qué recomendaciones de seguridad o buenas prácticas deben tenerse en cuenta.

Todos los integrantes del grupo deberán participar en la exposición.

### 14.8. Criterios de evaluación

| Criterio | Descripción |
| --- | --- |
| Instalación funcional | La pila LAMP está instalada y las comprobaciones demuestran que funciona. |
| Dominio de la parte asignada | El grupo comprende, configura y justifica correctamente Apache, MySQL/MariaDB o PHP. |
| Calidad de la guía | La documentación es completa, ordenada, técnica y reproducible. |
| Documentación de incidencias | Se incluyen errores, sus causas y las soluciones aplicadas. |
| Evidencias | Se aportan comandos, capturas, configuraciones y pruebas de funcionamiento. |
| Exposición | La explicación es clara, técnica, organizada y cuenta con la participación de todo el grupo. |
| Trabajo en equipo | Se observa coordinación, reparto equilibrado y participación de los integrantes. |

