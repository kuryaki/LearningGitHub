## Init

Primero inicializar el repositorio con __git init <nombreRepositorio>__
tambien se puede inicializar una carpeta ya existente ej

    $ cd nombreRepositorio
    nombreRepositorio/$ git init

## Conf

Para poder ver que configuraciones tenemos usamos __git conf__
ej. el editor de commits o el nombre de usuario

    $ cd nombreRepositorio
    nombreRepositorio/$ git conf -l

-l lista todas las configuraciones

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

El commando __diff__ permite ver a detalle cuales son los cambios que estan
pendientes, con *--* muestra los archivos como se encuentran en el repositorio 
y con *++* los archivos como estan actualmente
    
