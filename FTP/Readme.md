# Servidor Linux (Ubuntu 20.04), servicio de FTP

![FTP Linux](https://codeablemagazine.com/wp-content/uploads/2016/10/ftp.jpg)

[Video]()

### Para realizar esta practica solo dispondremos de un Servidor DNS con un registro a nuesto servidor (ftp.safehome.local)

### Primero pasaremos a actualizar el servidor 

### Para instalar el servicio FTP 

**apt install proftpd**

### Veremos el estado de nuestro servicio en el servidor (Por defecto el servicio viene inactive)
 
 _Dos maneras de ver el estado del servicio_
**service proftpd status**
**systemctl status proftpd**

### Nos Dirigimos 

nano /etc/proftpd/proftpd.conf

 
### Configuraciones ProFTPd
 
 [ DefaultRoot - Ruta de acceso ]
 [ DefaultRoot - Ruta de acceso Grupo/Usuario]
 
 [ ServerName (Nombre del Server) ]
 [ AccessGrantMsg (Mensaje de Conexion Establecida) ]
 [ AccessDenyMsg  (Mensaje de No Conectado) ]
 
 <Limit LOGIN>
 DenyAll
 AllowUser (usuario)
 </Limit>
 
 systemctl restart proftpd
 
### Crear usuarios 
 
 adduser (Nombre de Usuario)
 
 passwd (Usuario Creado)
 
 
### Logs
 
 var/log/proftpd/proftpd.log
 
 
### Verficacion de Conexiones en el Server
 
 ftpwho
 ftptop
