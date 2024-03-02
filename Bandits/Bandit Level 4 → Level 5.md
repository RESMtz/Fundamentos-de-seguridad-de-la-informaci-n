## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio interno. Consejo: si tu terminal está estropeado, prueba el comando “reset”.

## Solución 
bandit4@bandit:~/inhere$ find -type f -exec file {} +
./-file01: data
./-file02: data
./-file08: data
./-file06: data
./-file00: data
./-file04: data
./-file05: data
./-file07: ASCII text
./-file03: data
./-file09: data
bandit4@bandit:~/inhere$ cat file07
cat: file07: No such file or directory
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat -file07
cat: invalid option -- 'f'
Try 'cat --help' for more information.
bandit4@bandit:~/inhere$ cat<-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Contraseña obtenida en este nivel 
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Notas 

