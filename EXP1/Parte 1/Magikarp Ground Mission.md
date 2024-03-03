## Descripción del reto
¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicie el contenedor, "ssh" y luego "ls" una vez conectado para comenzar. Inicie sesión a través de `ssh` como `ctf-player` con la contraseña, `481e7b14`
Detalles adicionales estarán disponibles después de lanzar su instancia de desafío.

## Pistas 
¡Encontrar una hoja de referencia para bash sería realmente útil!
## Solución 
Primeramente hacemos la conexión a través de ssh y ponemos nuestra contraseña: 
resm-picoctf@webshell:/$ ssh ctf-player@venus.picoctf.net -p 55053
The authenticity of host '[venus.picoctf.net]:55053 ([3.131.124.143]:55053)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:55053' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.
To restore this content, you can run the 'unminimize' command.
The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.
Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Una vez dentro del usuario aplicamos ls para ver que necesitamos 
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt

Aplicamos cat para ver las instrucciones y hacer lo que se nos indica:
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`

Aplicamos cat para saber que es lo que se tiene dentro de un archivo: 
ctf-player@pico-chall$ cat 1of3.flag.txt           
picoCTF{xxsh_
(Aquí se obtiene la primera parte de nuestra bandera)

Aquí se ejecuta cat para ver las instrucciones que se requieran para poder obtener 
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`

Cambiamos de directorio debido a la pista y aplicamos nuevamente el procemiento de la parte 1 y dos :
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`

ctf-player@pico-chall$ cd ~

ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in

ctf-player@pico-chall$ cat 3of3.flag.txt
1118a9a4}
## Contraseña obtenida 
picoCTF{xxsh_0ut_0f_\/\/4t3r_1118a9a4}
## Notas 
Es importante saber navegar entre los directorios, aunque a veces las carpetas a simple vista no se periban nos puden ayudar bastante, ya que podemos observar que así pude concatenar las partes de mi contraseña.
## Referencias 
No use referencias, ya que como tal. Se tenía conocimiento previo sobre los comandos ya aplicados.
