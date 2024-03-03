## Descripción del reto
Este archivo tiene una bandera a la vista (también conocida como "claro"). Descargar bandera.
## Pistas 
1.- Cualquier sugerencia sobre cómo ingresar un comando en la Terminal (como el siguiente) comenzará con un '$'... todo lo que esté después del signo de dólar se escribirá (o se copiará y pegará) en su Terminal.

2.- Para que se pueda acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal: $ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag

3.- $ man cat

## Solución 

1.- Primero lo que hice con el comando mkdir, después previamente descargue mi archivo en la consola virtual con el comando wget acompañado del link de descarga del archivo, después de eso ejecute el comando cat, para poder obtener nuestra contraseña: 
resm-picoctf@webshell:~$ cd obdient-cat/
resm-picoctf@webshell:~/obdient-cat$ ls
resm-picoctf@webshell:~/obdient-cat$ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
--2024-03-03 06:28:13--  https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                            100%[======================================================================================================>]      34  --.-KB/s    in 0s      

2024-03-03 06:28:13 (16.9 MB/s) - 'flag' saved [34/34]

resm-picoctf@webshell:~/obdient-cat$ ls
flag
resm-picoctf@webshell:~/obdient-cat$ cat flag
picoCTF{s4n1ty_v3r1f13d_f28ac910}
## Contraseña obtenida 
picoCTF{s4n1ty_v3r1f13d_f28ac910}
## Notas 
En este nivel no aprendí nada nuevo, ya que se usaron comandos anteriores, como lo es cat.
## Referencias 

No cuento con referencias, ya que este comando tenía conocimientos previos sobre ellos.
