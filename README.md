# GIT 101

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

# GIT 201

## branch

Una rama es un nuevo camino del codigo que debe ser manejado pero que no esta listo para
ser incluido en el *master* del repositorio, ej. nuevas funcionalidades

__git branch__ sin argumentos lista la ramas disponibles y con un asterisco la actual 
__git branch -v__ Lista las ramas y muestra el ultimo commit en cada una 
__git branch <nombreRama>__ crea una rama para trabajar
__git branch checkout <nombreRama>__ cambia la rama de trabajo a la rama seleccionada
__git branch checkout master__ vuelve a la rama principal (trunk?)
__git branch -D <nombreRama>__ elimina la rama

Todos los commits que se realizen estando trabajando en una rama quedan en la rama y se puede
cambiar entre ramas sin que los cambios realizados en una u otra se vean reflejados antes 
de hacer una mezcla (*ver adelante*)


