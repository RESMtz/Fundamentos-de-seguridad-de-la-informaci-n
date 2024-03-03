## Descripción del reto
¿Puedes mirar los datos en este binario: estático? ¡Este script BASH podría ayudar!
## Pistas 
No hay pistas 
## Solución 

Comenzamos descargando el archivo con wget y comprobamos con ls para ver si la descarga fue ejecutada:
`resm-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static`
`--2024-03-02 07:17:18--  https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static`
`Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142`
`Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 8376 (8.2K) [application/octet-stream]`
`Saving to: 'static'`

`static                                          100%[======================================================================================================>]   8.18K  --.-KB/s    in 0s`      

`2024-03-02 07:17:18 (334 MB/s) - 'static' saved [8376/8376]`

`resm-picoctf@webshell:~$ ls`
`README.txt  flag  flag.1  index.html  index.html.1  ltdis.sh  static  warm`

Después comprobe con el comando file lo del archivo, para observar que tipo de archivo es
`resm-picoctf@webshell:~$ file ltdis.sh`
`ltdis.sh: Bourne-Again shell script, ASCII text executable`
`resm-picoctf@webshell:~$ file static`
`static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=639391a8b15c579d69659462d3c935fa61693f17, not stripped`
`resm-picoctf@webshell:~$ cat ltdis.sh`
`#!/bin/bash`
`echo "Attempting disassembly of $1 ..."`
`#This usage of "objdump" disassembles all (-D) of the first file given by` 
`#invoker, but only prints out the ".text" section (-j .text) (only section`
`#that matters in almost any compiled program...`
`objdump -Dj .text $1 > $1.ltdis.x86_64.txt`
`#Check that $1.ltdis.x86_64.txt is non-empty`
`#Continue if it is, otherwise print error and eject`
`if [ -s "$1.ltdis.x86_64.txt" ]`
`then`
        `echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"`
	      `echo "Ripping strings from binary with file offsets..."`
        `strings -a -t x $1 > $1.ltdis.strings.txt`
        `echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"`
`else`
        `echo "Disassembly failed!"`
        `echo "Usage: ltdis.sh <program-file>"`
        `echo "Bye!"`
`fi`
`resm-picoctf@webshell:~$ ls`
`README.txt  flag  flag.1  index.html  index.html.1  ltdis.sh  static  warm`

Finalmente aplique el comando strings para ver las cadenas, con un pipe acompañado de un grep para encontrar las cadenas que contengan pico y podamos encotrar nuestra bandera.
`resm-picoctf@webshell:~$ strings static | grep pico`

`picoCTF{d15a5m_t34s3r_98d35619}`
## Contraseña obtenida 
picoCTF{d15a5m_t34s3r_98d35619}
## Notas 
Aquí pude diferenciar la importancia que tiene el comando strings y grep ya que nos pueden ayudar ambos a distintas cosas por ejemplo el comando strings unicamente se centra en enviar cadenas de un archivo en cambio el comando grep nos ayuda a poder buscar una cadena o elemento con distintas caracteristicas.
## Referencias 
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.
https://francisconi.org/linux/comandos/strings

