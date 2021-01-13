---
layout: default
---

[Atras](../Readme.md)

## DNS

_El sistema de nombres de dominio ​ es un sistema de nomenclatura jerárquico descentralizado para dispositivos conectados a redes IP como Internet o una red privada_

## Domain Name Server (DNS)

_Un servidor de nombres es un servidor de hardware o software que implementa un servicio de red para proveer respuestas a las consultas en un servicio de directorio. Traduce un identificador basado en texto a una identificación numérica o componente de direccionamiento interno de sistema. Este servicio es realizado por el servidor en respuesta a una petición de protocolo de servicio_

## Notas

_El proceso de traducción de los nombres de dominio en direcciones numéricas que las máquinas puedan entender es lo que se conoce como resolución de nombres, una labor que realiza el Domain Name System, en castellano Sistema de Nombres de Dominio, conocido por sus siglas DNS._

**_Para configurar un servicio de DNS se necesita tener una IP fija_**

_-> Revisar el archivo /etc/network/interfaces_
_-> Tener una puerta de enlace para la cual tener internet y poder descargar los paquetes necesarios_

### Tipos de Registros DNS

* _A = Dirección (address). Este registro se usa para traducir nombres de servidores de alojamiento a direcciones IPv4._
* _AAAA = Dirección (address). Este registro se usa en IPv6 para traducir nombres de hosts a direcciones IPv6.:
* _CNAME = Nombre canónico (canonical Name). Se usa para crear nombres de servidores de alojamiento adicionales, o alias, para los servidores de alojamiento de un dominio. Es usado cuando se están corriendo múltiples servicios (como FTP y servidor web) en un servidor con una sola dirección IP. Cada servicio tiene su propia entrada de DNS (como ftp.ejemplo.com. y www.ejemplo.com.). Esto también es usado cuando corres múltiples servidores HTTP, con diferentes nombres, sobre el mismo host. Se escribe primero el alias y luego el nombre real. Ej. Ejemplo1 IN CNAME ejemplo2_
* _NS = Servidor de nombres (name server). Define la asociación que existe entre un nombre de dominio y los servidores de nombres que almacenan la información de dicho dominio. Cada dominio se puede asociar a una cantidad cualquiera de * servidores de nombres._
* _MX = Intercambio de correo (mail exchange). Asocia un nombre de dominio a una lista de servidores de intercambio de correo para ese dominio. Tiene un balanceo de carga y prioridad para el uso de uno o más servicios de correo._
* _PTR = Indicador (pointer). También conocido como 'registro inverso', funciona a la inversa del registro A, traduciendo IPs en nombres de dominio. Se usa en el archivo de configuración de la zona DNS inversa._
* _SOA = Autoridad de la zona (start of authority). Proporciona información sobre el servidor DNS primario de la zona._
* _SRV = Service record (SRV record)._
* _ANY = Toda la información de todos los tipos que exista. (No es un tipo de registro, sino un tipo de consulta)_

### Ejemplo

```dns
x.example.       MX   10 a.x.example.
*.x.example.     MX   10 a.x.example.
*.a.x.example.   MX   10 a.x.example.
a.x.example.     MX   10 a.x.example.
a.x.example.     AAAA 2001:db8::1
```

## Video

[Video](https://youtu.be/_6d7BgY6_sU)
