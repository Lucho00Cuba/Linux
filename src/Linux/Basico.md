## Conceptos Basicos

**.** = Directorio Actual
```markdown
lucho@linux:~$ ls .
Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap test Vídeos
lucho@linux:~$
```

**..** = Directorio Padre
```markdown
lucho@linux:~$ ls ..
lucho
lucho@linux:~$
```

### Rutas

**Ruta Relativa**
```markdown
lucho@linux:~$ ls ./Escritorio
lucho@linux:~$
```

**Ruta Completa** 
```markdown
lucho@linux:~$ ls /home
lucho@linux:~$
```

## Comandos Basicos de Linux

* pwd 
    * Directorio de Trabajo
        ```markdown
        lucho@linux:~$ pwd
        /home/lucho
        lucho@linux:~$  
        ```
* cat
    * Ver contenido de archivos
        ```markdown
        lucho@linux:~$ cat archivo.txt
        Hola Mundo
        lucho@linux:~$
        ```
* ls
    * Listar directorios
        ```markdown
        lucho@linux:~$ ls
        Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap  Vídeos
        lucho@linux:~$
        ```
* cd
    * Moverse por los directorios
        ```markdown
        lucho@linux:~$ cd Escritorio
        lucho@linux:~/Escritorio$
        ```
* mkdir
    * Creacion de directorios
        ```markdown
        lucho@linux:~$ mkdir test
        lucho@linux:~$ ls
        Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap test Vídeos
        lucho@linux:~$
        ```
* touch
    * Creacion de archivos
        ```markdown
        lucho@linux:~$ touch test.txt
        lucho@linux:~$ ls
        Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap test.txt Vídeos
        lucho@linux:~$
        ```
* rm 
    * Eliminar archivos y directorios
        ```markdown
        lucho@linux:~$ rm test.txt
        lucho@linux:~$ ls
        Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap Vídeos
        lucho@linux:~$
        ```
* rmdir
    * Eliminar directorios o subdirectorios **vacios**
        ```markdown
        lucho@linux:~$ rmdir test
        lucho@linux:~$ ls
        Descargas  Documentos  Escritorio  Imágenes  Música  Plantillas  Público  snap Vídeos
        lucho@linux:~$
        ```
* history
    * Ver historial de comandos introducidos
        ```markdown
        lucho@linux:~$ history
        1   pwd
        2   cat archivo.txt
        3   ls
        4   cd Escritorio
        5   mkdir test
        6   touch test.txt
        7   rm test.txt
        8   rmdir test
        9   history
        lucho@linux:~$
        ```

* echo
    * Imprimir en consola
        ```markdown
        lucho@linux:~$ echo "Hola Mundo"
        Hola Mundo
        lucho@linux:~$
        ```

* mv 
    * Cambiar directorios, archivos de ruta o nombre
        ```markdown
        lucho@linux:~$ mv archivo.txt ./Escritorio
        lucho@linux:~$
        ```

* cp 
    * Copiar directorios y archivos
        ```markdown
        lucho@linux:~$ cp archivo.txt ./Documentos
        lucho@linux:~$
        ```
