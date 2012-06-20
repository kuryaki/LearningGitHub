h2. Init

Primero inicializar el repositorio con __git init <nombreRepositorio>__

h2. Conf

Para poder ver que configuraciones tenemos usamos __git conf__
ej. el editor de commits o el nombre de usuario

    $ cd nombreRepositorio
    nombreRepositorio/$ git conf -l

-l lista todas las configuraciones

h2. Add

Para poder agregar algo a un commit hay que crearlo y luego agregarlo con __git add__

    $vim README.md
    -- hacer algo alli --
    $git add README.md

tambien se puede usar __git add -A__ para agregar a un commit todos los cambios
*USAR CON PRECAUCION*

h2. Commit

Hacer un commit (comprometerse con un cambio :P) luego de agregar los cambios a un commit
se hace usando __git commit__

    $git commit

**-m** se puede usar para enviar en el commit el mensaje directamente ej. __git commit -m "Primer Commit"__
*USAR CON PRECAUCION*
    
