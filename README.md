# GIT 101 - Conceptos Basicos

## Init

Primero inicializar el repositorio con __git init <nombreRepositorio>__
tambien se puede inicializar una carpeta ya existente ej

    $ cd nombreRepositorio
    nombreRepositorio/$ git init

## Config

Para poder ver que configuraciones tenemos usamos __git config__
ej. el editor de commits o el nombre de usuario

    $ cd nombreRepositorio
    nombreRepositorio/$ git config -l

-l lista todas las configuraciones

    $ git config --global user.name "Su Nombre"
    $ git config --global user.email "Su Correo"
    $ git config --global core.editor "Su Editor ej. notepad"

Esto se hace para configurar la instalacion/repositorio

## Add

Para poder agregar algo a un commit hay que crearlo y luego agregarlo con __git add__

    $ vim README.md
    -- hacer algo alli --
    $ git add README.md

tambien se puede usar __git add -A__ para agregar a un commit todos los cambios
*USAR CON PRECAUCION*

## Commit

Hacer un commit (comprometerse con un cambio :P) luego de agregar los cambios a un commit
se hace usando __git commit__

    $ git commit

**-m** se puede usar para enviar en el commit el mensaje directamente ej. __git commit -m "Primer Commit"__
*USAR CON PRECAUCION*

## Status

Permite visualizar si hay archivos que tienen ambios que pendientes de hacer commit/sobreescribir

    $ git status

## Diff

El commando __git diff__ permite ver a detalle cuales son los cambios que estan
pendientes, con *--* muestra los archivos como se encuentran en el repositorio 
y con *++* los archivos como estan actualmente

## Checkout

Con el commando __git checkout <nombreArchivo/Ficher>__ reemplazo mis cambios
locales por los cambios que se encuentran en el repositorio, adicionalmente me
permite cambiar entre ramas (*ver adelante*)

## Log

__git log__ muestra el log de los commits que se han realizado, incluyendo el mensaje,
el autor, y la fecha

# rm / mv

Con __git rm__ o __git mv__ se pueden eliminar o mover archivos o ficheros que se encuentran
en el repositorio

# GIT 201 - Ramas y Mezclas

## branch

Una rama es un nuevo camino del codigo que debe ser manejado pero que no esta listo para
ser incluido en el *master* del repositorio, (la rama master es la rama por defecto en git) 

las ramas se usan por ejemplo para manejar nuevas funcionalidades

__git branch__ sin argumentos lista la ramas disponibles y con un asterisco la actual 
__git branch -v__ Lista las ramas y muestra el ultimo commit en cada una 
__git branch <nombreRama>__ crea una rama para trabajar
__git branch checkout <nombreRama>__ cambia la rama de trabajo a la rama seleccionada
__git branch checkout master__ vuelve a la rama principal (trunk?)
__git branch -D <nombreRama>__ elimina la rama

Todos los commits que se realizen estando trabajando en una rama quedan en la rama y se puede
cambiar entre ramas sin que los cambios realizados en una u otra se vean reflejados antes 
de hacer una mezcla (*ver adelante*)

## merge

Luego de tener los cambios en una rama y estar seguros de estos hay que realizar una mezcla
existen diferentes estrategias para mezclar ej.
    
    branch->master
    master->branch
    branch->branch
    (branch<->branch)->branch

El commando __git merge__ nos permite hacer todo este tipo de mezclas, sin embargo solo vamos a
ver la mas basica, luego de realizar los cambios en nuestra rama:

    $ git checkout master                # pasamos al master
    $ git merge <nombreRama>             # mezclamos la rama en nuestro master

Si existen conflictos git nos mostrara los archivos donde se presentaron para que sean resueltos
manualmente

## tag / show

Cuando estamos seguros de una version de nuestro codigo y queremos marcarla como segura / estable
podemos crear un tag con __git tag <nombre del tag>__ para que quede una copia del repositorio
en ese momento, para listar los tags lo hacemos con __git tag -l__ y para ver especificamente que 
tiene un tag lo hacemos con __git show <nombre del tag>__

# GIT 301 - Compartiendo el codigo

## .gitignore

Algunos archivos no queremos que sean controlados o guardar copias de estos en el repositorio
por ejemplo .class / .pyc / .py~ etc, para esto creamos un archivo .gitignore que contiene
mediante expresiones regulares los archivos y tipos de archivos que no queremos controlar

## clone

Un repositorio de git esta listo para ser compartido desde el primero momento, para hacer una
copia de un repositorio se debe usar __git clone <ubicacion del repo>__

## SSH Keys

Antes de poder compartir nuestro codigo o colaborar con otros repositorios debemos identificarnos
de una forma que garantize nuestra autenticidad, para esto se usa la generacion de llaves SSH

    $ ssh-keygen

Esto nos genera una llave publica y una llave privada, debemos entregarle la llave publica a la 
persona que queremos que confie en nuestro codigo (ej. github)

## remote

Para poder conectarnos con un repositorio fuera del que tenemos tenemos tenemos que agregar un 
repositorio remoto con el commando __git remote add <nombre remoto> <ubicacion del repo>__ se
puede usar __git remote rm <nombre remoto>__ para borrarlo

## push

Luego de estar conectados a un repositorio podemos _empujar_ al repositorio remoto los cambios
que tenemos en nuestro repositorio local mediante __git push <nombre remoto> <nombre rama>__
por defecto git intenta empujar al remoto origin y a la rama master

## pull y fetch

Al igual que podemos empujar nuestros cambios a un repositorio remoto podemos jalar cambios de
un repositorio remoto a nuestro repositorio local bien sea a nuestro carpeta de trabajo (pull) 
o a la copia de nuestro repositorio (fetch) usando los comandos

__git pull <nombre remoto> <nombre rama>__
__git fetch <nombre remoto> <nombre rama>__

## Fork?

Un fork no es un concepto de Git, es mas una conveniencia social, donde se hace el clone de un 
repositorio bajo un nombre propio, como git genera una copia del repositorio a traves de un
clone, podemos trabajarlo como un
