---
layout: default
---

## Correo

_El protocolo de envio de correos en el (SMTP: El protocolo para transferencia simple de correo). En esta practica esrtaremos instalando un servidor de correo muy simple. Estaremos utilizando Postfix. Postfix es un servidor de correo de software libre / código abierto, un programa informático para el enrutamiento y envío de correo electrónico_

## Requisitos

_Tener ya configurado un servidor DNS. Con los registros correspondientes al servidor de correo_

**_Registros DNS_**
```markdown
mail            IN  A       10.15.1.10
safehome.local. IN  MX 10   mail
```

* safehome.local = Nombre DNS del servidor de correo
* 10.15.1.10 = La IP del servidor 

**+** [DNS by Lucho](../DNS/dns.md)

## Datos

* FQDN del servidor de correo = mail.safehome.local
* Cliente Ubuntu
* **IMPORTANTE** : _El servidor que estamos realizando en la practica tiene seguridad nula, solo como medio de aprendizaje basico, no para produccion_

## Configuraciones

_Nota : Todas las configuraciones vistas aqui se muetran en el video_

### Creacion de usuarios para el servidor de correo

```markdowm
root@server:~# adduser
```

### Instalar Servidor SMTP (Postfix)

```markdown
root@server:~# apt-get install postfix -y
```

### Postfix

```markdown
root@server:~# nano /etc/postfix/main.cf
```

**Parametros a revisar o agregar**

* myhostname
* myorigin
* mydestination
* mynetwork
* inet_interfaces
* home_mailbox = Maildir/

### Verificar servicio

```markdown
root@server:~# systemctl restart postfix
root@server:~# systemctl status postfix
root@server:~# postconf -n
```

### Instalar Servidor IMAP y POP3 (Dovecot)

```markdown
root@server:~# apt-get install dovecot-core dovecot-imapd -y
```

**Configuraciones en el servidor imap**

* Deshabilitar SSL en el servidor 

```markdown
root@server:~# nano /etc/dovecot/conf.d/10-ssl.conf
```

* Habilitar las contraseñas en texto plano

```markdown
root@server:~# nano /etc/dovecot/conf.d/10-auth.conf
```

* Establecer tipo de buzon

```markdowm
root@server:~# nano /etc/dovecot/conf.d/10-mail.conf
```

### Verficar Servicio

```markdown
root@server:~# systemctl restart dovecot
root@server:~# systemctl status dovecot
``` 

## Listo ! Hacer las verificacion en los clientes

## Video 

[Video]()


