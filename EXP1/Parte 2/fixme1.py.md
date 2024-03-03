## Descripción del reto
## Pistas 
Corrija el error de sintaxis en este script de Python para imprimir la bandera.
Descargar el script Python
https://artifacts.picoctf.net/c/27/fixme1.py

## Solución 

Primero descargamos el archivo: 
`resm-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/27/fixme1.py`
`--2024-03-02 18:20:36--  https://artifacts.picoctf.net/c/27/fixme1.py`
`Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.43, ...`
`Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 837 [application/octet-stream]`
`Saving to: 'fixme1.py.1'`

`fixme1.py.1                                     100%[======================================================================================================>]     837  --.-KB/s    in 0s`      

`2024-03-02 18:20:36 (35.7 MB/s) - 'fixme1.py.1' saved [837/837]`

`resm-picoctf@webshell:~$ ls`
`Addadshashanammu      README.txt  codebook.txt  file    file.2     fixme1.py.1  flag.1      index.html.1  static`
`Addadshashanammu.zip  code.py     convertme.py  file.1  fixme1.py  flag         index.html  ltdis.sh      warm`

Ejectuamos el archivo .py y vemos cual es el problema. 
`resm-picoctf@webshell:~$ python fixme1.py`
  `File "/home/resm-picoctf/fixme1.py", line 17`
    `flag = str_xor(flag_enc, 'enkidu')`
`IndentationError: unexpected indent`
`resm-picoctf@webshell:~$ nano fixme1.py`

`resm-picoctf@webshell:~$ python fixme1.py`
`resm-picoctf@webshell:~$ nano fixme1.py`
`resm-picoctf@webshell:~$ python fixme1.py`
  `File "/home/resm-picoctf/fixme1.py", line 16`
    `flag = str_xor(flag_enc, 'enkidu')`
`IndentationError: unexpected indent`
Una vez encontrado el error lo corregimos y ejecutamos el archivo: 
`resm-picoctf@webshell:~$ nano fixme1.py`
`resm-picoctf@webshell:~$ python fixme1.py`
`That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}`
`resm-picoctf@webshell:~$` 

## Contraseña obtenida 
picoCTF{1nd3nt1ty_cr1515_182342f7}
## Notas 
Aquí mediante el comando nano pude hacer la edición del archivo con extensión .py nos marca error en cuanto a una linea, la cual era solo corregir la sintaxis.
## Referencias 
https://josesalazarpantoja.gitbooks.io/comandos-basicos-linux/content/comando-nano.html

