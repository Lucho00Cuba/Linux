---
layout: default
---

[Atras](../../index.md)

## Servicio SSH

_SSH es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada_

## Instalar

* Debian, Ubuntu
    ```shell
    apt install openssh-server openssh-client
    ```

* Centos
    ```shell
    yum -y install openssh-server openssh-client
    ```

## Estado del servicio

```shell
systemctl status sshd
```

## Archivo de Configuracion

```shell
cat /etc/ssh/sshd_config
```

## Consejos de Seguridad

_Estos son una serie de recomendaciones para nuestro servicio ssh_

_/etc/ssh/sshd_config_
```shell
PermitRootLogin no # -> No permitir el acceso con root
Port 2222 # -> Cambiar el puerto por defecto que es 22
```