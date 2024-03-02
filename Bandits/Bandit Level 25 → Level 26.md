## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

Iniciar sesión en bandit26 desde bandit25 debería ser bastante fácil... El shell para el usuario bandit26 no es /bin/bash, sino algo más. Descubra qué es, cómo funciona y cómo salir de él.
## Datos de usuario del nivel anterior

Usuario: ssh bandit25@bandit.labs.overthewire.org -p 2220
Contraseña: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución 
1.- Aplicamos ls -la para ver que se tiene dentro:
bandit25@bandit:~$ ls -la
total 32
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r-----  1 bandit25 bandit25   33 Oct  5 06:19 .bandit24.password
-r--------  1 bandit25 bandit25 1679 Oct  5 06:19 bandit26.sshkey
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit25 bandit25    4 Oct  5 06:19 .pin
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
Ahora ls: 
bandit25@bandit:~$ ls
bandit26.sshkey

Usamos: 
bandit25@bandit:~$ cat /etc/passwd
Pero como nos arroja muchas lineas de codigo entonces cocatenamos con grep para hacer exclusividad al usuario 26

bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext


2.- Una ahí cambiamos de directorio al: /usr/bin/showtext
Que nos muestra lo siguiente: 
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0

3.- Finalmente hacemos la conexión por medio de ssh aplicando -i y llamando nuestro archivo que nos servira de local host para logearnos al usuario 26:
bandit25@bandit:~$ ssh bandit26@localhost -i bandit26.sshkey

4.- Ejectuamos cat a la carpeta donde se almacena nuestra password:

bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## Contraseña obtenida en este nivel 
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## Notas
En el nivel 17 se aplicó el mismo método que permite usar el ssh con un archivo llave entre medio. Aquí cabe recalcar que acudí a notas anteriores para poder acceder al siguiente nivel. Mientras que nos auxiliamos y aprendí un poco más sobre como usar nuestro comando More.

## Referencias 
https://axarnet.es/blog/ssh#:~:text=Para%20conectarte%2C%20utiliza%20el%20comando,en%20la%20l%C3%ADnea%20de%20comandos.
https://keepcoding.io/blog/que-es-el-comando-grep-y-como-usarlo-en-linux/
https://guias.donweb.com/comando-grep-en-linux/
