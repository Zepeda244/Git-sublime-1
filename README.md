![](https://assets-cdn.github.com/images/modules/open_graph/github-octocat.png)

---
# Curso Trabajo en equipo con GIT-GITHUB
---
## Git-bash
*El git bash, es una herramienta de tipo consola que básicamente te permite manipular y gestionar todo el proceso a realizar con el proyecto.
Es de aclarar que la explicación inicial se hace basada en Windows, sin embargo su funcionalidad es igual en cualquier sistema operativo.*

## Definir el nombre de nuestro proyecto:

*Debe ubicarse por consola en la carpeta donde guardará su proyecto, tenga en cuenta que no importa la ubicación de la carpeta donde tiene guardado su archivo o proyecto, cuando este ubicado en su carpeta deberá iniciar o registrar su proyecto con git usando el siguiente comando:*

    git config --global user.name "NOMBRE DEL AUTOR"

>“Si se llegase a equivocar solo vuelva a usar el comando”

## Ver el nombre ingresado del proyecto:
## Para ello se usa el comando:
    git config --global user.name
## Definir el correo electrónico:
    git config --global user.mail "CORREO ELECTRONICO"
## Ver el correo definido se usa:
    git config --global user.mail
## Definir los colores para distinguir estados:
    git config --global color.ui true
## Ver la configuración global de colores:
    git config --global --list
### DEFINICIÓN DEL PROYECTO A USAR GIT:
#### Ubíquese en la carpeta donde aplicara git
### En la carpeta de inicio al monitoreo del proyecto
    git init
### Ver el estado de nuestro proyecto monitoreado
    git status
### Si existe algún cambio el sistema le indicara en letras rojas al frente del archivo modificado el mensaje:
    modified: nombrearchivo.ext
### Ver que archivos están listos para ser agregados:
    git add
### Agregar un archivo, y cuando ya existe agrega el modificado
    git add archivo.ext
### Ver los cambios
    git status <-- Nos confirma si ya agregamos archivo.ext
### Agregar todos los archivos, si ya existen solo agrega los modificados
    git add -A
### Agregar mensaje al cambio registrado para identificar el cambio
    git commit -m "Mensaje" <-- Permite identificar cada cambio
### Listar cambios de todos los commits, mostrando toda la información
    D:\PROYECTO\>git log
    commit 2ea6ea0c8d223b074a94451332e2de59c32b909b
    Author: NOMBRE DEL AUTOR <CORREO ELECTRONICO>
    Date: Fri Mar 11 18:22:12 2016 -0500
### Cambio de la página de bienvenida
    commit 1118872dee888c449a9e757f2f1832c1122ae35f
    Author: NOMBRE DEL AUTOR <CORREO ELECTRONICO>
    Date: Fri Mar 11 18:11:45 2016 -0500
### Inicio del proyecto 11032016
## En la anterior lista se observa al frente de commit el código sha que identifica a cada commit
### Para recorrer los cambios del proyecto y recorrerlo en espacio de tiempo a través de su commits y ramas se utiliza:
    git checkout
## Para ir a un commit específico se utiliza
    git chekout 1118872dee888c449a9e757f2f1832c1122ae35f
    <– Código sha del commit
## Dentro de la ejecución mostrar el mensaje que confirma el cambio:
    HEAD is now at 1118872… Inicio del proyecto 11032016
## Como resultado mostrará el código que corresponde a ese estado del tiempo
## Si se usa git log mostrará solo el commit donde este ubicado:
    git log
    commit 1118872dee888c449a9e757f2f1832c1122ae35f
    Author: NOMBRE DEL AUTOR <CORREO ELECTRONICO>
    Date: Fri Mar 11 18:11:45 2016 -0500
## Inicio del proyecto 11032016
## Moverse al último commit creado:
    git checkout master
## Al validarse con:
    D:\PROYECTO\>git log
## Mostrará todos los commits creados
## Similar a checkout pero sirve para eliminar los commits
     git reset
###TIPOS DE GIT RESET
### Hay varios tipos de git reset
###No se mete con wl working area (es decir no toca nuestro código)
    git reset --soft
### Borra el Staging area, sin tocar el working area
    git reset --mixed
### Borra absolutamente todo lo que hay en el commit
    git reset --hard
### Extrae la lista de commits a un archivo texto
    git log > commits.txt
### Suponga que va a borrar un commit
    git reset --soft 1118872dee888c449a9e757f2f1832c1122ae35f
### Si se usa git log se observara que ya no aparece el commit borrado
## Si se usa el git status se observara que puede haber archivos que no se hayan ingresado a registrar el cambio
## El archivo generado con el nombre .DS_Store no hay que ponerle atención
### Agregar los commits de un archivo de texto generado con el comando git log > commits.txt:
     git add commits.txt
### Al verificar con git status mostrara efectivamente los cambios ya hechos
#### Al usar git commit -m “NUEVO MENSAJE” ingresara el nuevo mensaje en el commit encontrado en el archivo en el cual no existia previamente
### Borra el commit completo y el código que tuviera
    git reset --hard 1118872dee888c449a9e757f2f1832c1122ae35f
### Nos ayuda a saber como funciona git o alguno de sus comandos
    git help status
     git help add
## Para salir se usa q
## MANEJO DE RAMAS Y FUNCIONES
    Head -> es el commit donde nos entramos
    Ramas -> es una linea de tiempo de nuestro proyecto
    Rama Master -> es una linea de tiempo de nuestro proyecto donde se comenzó a trabajar,
    es la rama principal y estable de nuestro proyecto
### Crear una rama:
    git branch NombredelaRama <-- NombredelaRama es el nombre de nuestra rama
### Ver las ramas
    git branch
#### Para movernos entre las ramas usamos:
    git checkout NombredelaRama
### Que al revisarla con git branch nos muestra en verde y con asterisco la rama NombredelaRama
### Todos los cambios que se hagan a partir de ese momento quedarán en la rama NombredelaRama
#### Retornar a la rama principal
    git checkout master
### Borrar la rama:
    git branch -d NombredelaRama
### FUSIONAR RAMAS
### Fusiones es la creación de un nuevo commit uniendo una rama con otra
### Primero hay que ubicarse en la rama que va a absorber
    git checkout NombreRamaaAbsorber
### Para la fusión se usa el comando
    git merge RamaaSerAbsorbida
### TENGA EN CUENTA QUE AL FUSIONAR LE PUEDE SALIR DOS TIPOS DE MENSAJES
    Fast-Forward <– Simple y automático, cuando se trabaja con archivos diferentes o líneas de código distintas
    Manual Merge <– Largo y manual, antes de hacer la fusión pasa por las manos del usuario, pasa cuando se trabaja
    los mismos archivos o líneas de códgo.
### Las ramas se crean a partir de donde se encuentre
### Para borrar una rama específica se usa:
    git branch -D NombredelaRama
