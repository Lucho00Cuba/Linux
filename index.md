# Services Linux

You can use the [editor on GitHub](https://github.com/Lucho00Cuba/Services/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

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

_Buscamos y agregamos las siguientes configuraciones_

**Sustituir los [] por datos reales**

```markdown
DefaultRoot [Ruta de Acceso]
DefaulRoot  [Ruta de Acceso Grupo/Usuario]

ServerName  [Nombre del Servidor]

AccessGrantMsg  [Mensaje de Acceso Conseguido]
AccessDenyMsg   [Mensaje de Conexion Denegada]

<Limit LOGIN>
DenyAll
AllowUser [Usuario]
</Limit>
```

_Para salir y guardar Control+O y Control+X_

### Ya configurado el archivo de FTP conf

```markdown
root@server:~# systemctl restart proftpd
```

### Listo !!

_Ya estariamos listos para acceptar conexiones de nuestros clientes_

### Para ver los Logs del Servidor FTP

```markdown
root@server:~# cat /var/log/proftpd/proftpd.log
```

### Ver Conexiones en el Servidor

```markdown
root@server:~# ftpwho

root@server:~# ftptop
```

### Para mas informacion consultar el video del proceso

[Video]()