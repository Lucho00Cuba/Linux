---
layout: default
---

## Servicio FTP

_El Protocolo de transferencia de archivos (en inglés File Transfer Protocol o FTP) es un protocolo de red para la transferencia de archivos entre sistemas conectados a una red TCP (Transmission Control Protocol)_


### Notas

_Para levantar este servicio dispondremos de un servicio DNS en local para facilitar la conexion con el cliente. Si lo disponen de un servidor DNS lo podrian hacer con los numeros IPs de la maquinas_


### Instalar ProFTPd
```markdown
root@server:~# apt-get update

root@server:~# apt-get install proftpd -y
```
### Nos dirigimos a la ruta de configuracion del FTP

```markdown
root@server:~# nano /etc/proftpd/proftpd.conf
```

### En el archivo de configuracion de FTP

_El archivo de configuracion quedaria de esta manera_

```markdown
Include /etc/proftpd/modules.conf
UseIPv6				        on
IdentLookups			    off
ServerName			        "FTP SafeHome"
ServerType			        standalone
DeferWelcome			    off
MultilineRFC2228		    on
DefaultServer			    on
ShowSymlinks			    on
TimeoutNoTransfer		    600
TimeoutStalled			    600
TimeoutIdle			        1200
DisplayLogin                welcome.msg
DisplayChdir                .message true
ListOptions                 "-l"
DenyFilter			        \*.*/
Port				        21
<IfModule mod_dynmasq.c>
</IfModule>
MaxInstances			30
User				proftpd
Group				nogroup
Umask				022  022
AllowOverwrite			on
TransferLog /var/log/proftpd/xferlog
SystemLog   /var/log/proftpd/proftpd.log
<IfModule mod_quotatab.c>
QuotaEngine off
</IfModule>
<IfModule mod_ratio.c>
Ratios off
</IfModule>
<IfModule mod_delay.c>
DelayEngine on
</IfModule>
<IfModule mod_ctrls.c>
ControlsEngine        off
ControlsMaxClients    2
ControlsLog           /var/log/proftpd/controls.log
ControlsInterval      5
ControlsSocket        /var/run/proftpd/proftpd.sock
</IfModule>
<IfModule mod_ctrls_admin.c>
AdminControlsEngine off
</IfModule>
Include /etc/proftpd/conf.d/

AccessGrantMSG  "Bienvenido al FTP de SafeHome"
AccessDenyMSG   "Error al entrar al FTP de SafeHome"

DefaultRoot ~
```

_Para salir y guardar Control+O y Control+X_

### Ya configurado el archivo de FTP conf

```markdown
root@server:~# systemctl reload proftpd
```

### Listo !!

_Ya estariamos listos para acceptar conexiones de nuestros clientes_

## -----------------------------------------------------------------------------

## * Aportes  

### Ver Conexiones en el Servidor

```markdown
root@server:~# ftpwho

root@server:~# ftptop
```

### Verficar Logs del Servidor FTP
```markdown 
root@server:~# tail -n 15 /var/log/proftpd/proftpd.log
```

### Para mas informacion consultar el video del proceso

[Video](https://youtu.be/6lRS8G4Oo8w)