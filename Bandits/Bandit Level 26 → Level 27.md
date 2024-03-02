## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!


## Datos de usuario del nivel anterior

Usuario: ssh bandit26@bandit.labs.overthewire.org -p 2220
Contraseña:  c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## Solución 
1.- Para empezar aplicamos el comando ls para ver que hay dentro:
bandit26@bandit:~$
bandit26@bandit:~$ ls
bandit27-do  text.txt
2.- Vemos que hay un texto y un ejecutable entonces aplicamos un cat al texto 
bandit26@bandit:~$ cat text.txt
3.- No pasa nada como se observa entonces recurrimos a ejectuarlo como se observa a continuación para ver que usuarios estan haciendo uso del usuario:
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)


bandit26@bandit:~$ ls -l bandit27-do
-rwsr-x--- 1 bandit27 bandit26 14876 Oct  5 06:19 bandit27-do

4.- Finalmente ejecutamos el archivo que esta ahí junto a su dirección para poder ver que hay dentro de nuestro archivo e incluso se le introduce la ruta para poder acceder a la contraseña
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS


## Contraseña obtenida en este nivel 
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
## Notas 
Pudimos aplicar conocimiento previo de niveles además del visto en clase, ya que algunos comandos se repiten
## Referencias 
