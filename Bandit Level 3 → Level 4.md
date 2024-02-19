## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio interno.
## Solución 
Entramos al usuario del nivel anterior 
Una vez ahí aplicamos los siguientes comandos: 
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
## Contraseña obtenida en este nivel 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
## Notas 
Podemos observar que cd nos ayuda a acceder a los directorios y el comando ls -a nos muestra los archivos incluso ocultos 
