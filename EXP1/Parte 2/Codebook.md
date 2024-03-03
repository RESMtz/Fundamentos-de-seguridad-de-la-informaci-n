## Descripción del reto
## Pistas 
## Solución 

Primero descargue el archivo como es costumbre, despues de guardar aplique ls para poder corroborar que se guardo:
resm-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2024-03-02 16:50:27--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                         100%[======================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-03-02 16:50:27 (539 MB/s) - 'code.py' saved [1278/1278]

resm-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  code.py  flag  flag.1  index.html  index.html.1  ltdis.sh  static  warm

Una vez ahí dentro, buscamos como ejecutar los archivos con la extensión .py

resm-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
## Contraseña obtenida
picoCTF{c0d3b00k_455157_197a982c}
## Notas 
Aquí pude adquirir la habilidad de poder ejectuar, el archivo con la extensión .py en este caso se refiere a python y fue de la manera con la cual pude ejectarlo.
## Referencias 
https://platzi.com/tutoriales/1474-oop/9286-como-ejecutar-programas-py-en-ubuntu/

