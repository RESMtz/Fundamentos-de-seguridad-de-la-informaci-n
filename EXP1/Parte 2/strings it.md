## Descripción del reto
¿Puedes encontrar la bandera en el archivo sin ejecutarla?
## Pistas 
https://linux.die.net/man/1/strings
## Solución
Primero cree mi directorio, para despues descargar y aplicar ls para corroborar que existe el archivo:
m-picoctf@webshell:~$ mkdir nivel15exp1
resm-picoctf@webshell:~$ cd nivel15exp1 
resm-picoctf@webshell:~/nivel15exp1$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2024-03-02 18:36:34--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                         100%[======================================================================================================>] 757.84K  1.86MB/s    in 0.4s    

2024-03-02 18:36:34 (1.86 MB/s) - 'strings' saved [776032/776032]

resm-picoctf@webshell:~/nivel15exp1$ ls
strings

Mediante el comando strings, como dice la descripción sin ejecutarlo nos apoyamos para poder ver lo que hay dentro en formato texto, y apoyando con un pipe podemos obtener con grep la cadena especifica con grep:

resm-picoctf@webshell:~/nivel15exp1$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_7f766a23}
## Contraseña obtenida 
picoCTF{5tRIng5_1T_7f766a23}
## Notas 
Es importante saber extraer datos mediante archivos que no necesariamente tengan que ser ejecutados en su proceso para poder observar que podemos obtener, lo malo que no siempre todo será en texto legible como lo es en este caso.
## Referencias
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.
https://francisconi.org/linux/comandos/strings


