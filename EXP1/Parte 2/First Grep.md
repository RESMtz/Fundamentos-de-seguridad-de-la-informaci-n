## Descripción del reto
## Pistas 
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)
https://ryanstutorials.net/linuxtutorial/grep.php

## Solución
resm-picoctf@webshell:~$ cd FristGrep/
resm-picoctf@webshell:~/FristGrep$ wget https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
--2024-03-03 08:34:57--  https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                                            100%[======================================================================================================>]  14.21K  --.-KB/s    in 0s      

2024-03-03 08:34:57 (411 MB/s) - 'file' saved [14551/14551]
resm-picoctf@webshell:~/FristGrep$ grep "picoCTF" file
picoCTF{grep_is_good_to_find_things_5af9d829}

## Contraseña obtenida 
picoCTF{grep_is_good_to_find_things_5af9d829}
## Notas 
Pude aplicar el comando grep para poder buscar una cadena en especifico y así tener la facilidad de poder encontrar dicha cadena dentro del archivo.
## Referencias 
https://www.hostinger.mx/tutoriales/comando-grep-linux

