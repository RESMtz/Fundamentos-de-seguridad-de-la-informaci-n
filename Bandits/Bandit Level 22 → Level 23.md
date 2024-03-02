## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

Un programa se ejecuta automáticamente a intervalos regulares desde cron, el programador de trabajos basado en el tiempo. Busque en /etc/cron.d/ la configuración y vea qué comando se está ejecutando.

NOTA: Mirar scripts de shell escritos por otras personas es una habilidad muy útil. El guión de este nivel se ha hecho intencionadamente fácil de leer. Si tiene problemas para entender lo que hace, intente ejecutarlo para ver la información de depuración que imprime.
## Datos de usuario
Usuario: ssh bandit22@bandit.labs.overthewire.org -p 2220
Contraseña: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
## Solución 
1.- Primeramente como se nos pide una vez dentro del usuario accedemos al directorio en etc/cron.d/ :
bandit22@bandit:~$ cd  /etc/cron.d/

2.- Una vez ahí ingresamos ls, para poder observar lo que se encuentra dentro del directorio:
bandit22@bandit:~$ cd  /etc/cron.d/
bandit22@bandit:/etc/cron.d$ ls -a
.   cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  .placeholder
..  cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir  sysstat

3.- Una vez ahí a través del comando CAT para ver que hay a través del archivo del siguiente usuario en este caso lo usamos para saber el de usuario bandit23 en este caso usamos la siguiente linea de comando:   cat /etc/cron.d/cronjob_bandit23

Una vez ahí nos arroja la siguiente línea: 
@reboot bandit23 `/usr/bin/cronjob_bandit23.sh`  &> /dev/null
* * * * * bandit23 `/usr/bin/cronjob_bandit23.sh`  &> /dev/null
Una vez obteniendo estos datos podemos observar que podemos ejecutar nuevamente la ruta que se nos proporciono 
4.-  Ejectuamos la siguiente línea: 
`cat /usr/bin/cronjob_bandit23.sh`
Una vez ejecutada para ver lo que hay en nuestro directorio nos arroja el siguiente mensaje:
`bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh`
`#!/bin/bash`
`myname=$(whoami)`
`mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)`
`echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"`
`cat /etc/bandit_pass/$myname > /tmp/$mytarget`

5.- Al obtener esta línea: 
`mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)`
Podemos obtener otra pista a nuestra solución: 
`echo I am user Bandit23 | md5sum | cut -d ' ' -f 1`
Una vez ejecutado este comando nos arroja lo siguiente: 
`bandit22@bandit:~$  echo  I am user bandit23 | md5sum | cut -d ' ' -f 1`
`8ca319486bfbbc3663ea0fbe81326349``

6.- Como el comando anterior nos indica: 
`cat /etc/bandit_pass/$myname > /tmp/$mytarget`
Hacemos cambio con CD y $mytarget lo sustituimos de la siguiente manera: 
```bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349`

QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
## Contraseña obtenida en este nivel 
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
## Notas 
El comando Cron, es aquel que nos ayuda a administrar los procesos es un demonio comentado en clase y aunque en este nivel no lo implemente al 100% el comando que nos ayudo fue el Cat ya que este nos permite indagar y ver el contenido que nos ayuda a ver los datos de salida. En este nivel pude aprender a implementar mucho mejor y que útilidad tiene el cat.

## Referencias
https://www.enmimaquinafunciona.com/pregunta/23188/que-significan-los-diferentes-colores-en-ls
https://www.redeszone.net/tutoriales/servidores/cron-crontab-linux-programar-tareas/
https://help.dreamhost.com/hc/es/articles/215767107-Entorno-de-ejecuci%C3%B3n-de-un-cron-job
