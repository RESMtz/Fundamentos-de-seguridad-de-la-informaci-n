## Descripción del reto
Corrija el error de sintaxis en el script de Python para imprimir la bandera.
Descargar el script Python
## Pistas 
1.- ¿Son la igualdad y la asignación el mismo símbolo?

2.- Para ver el archivo en el webshell, haga: $ nano fixme2.py

3.- Para salir de nano, presione Ctrl y x y siga las instrucciones en pantalla.

4.- No es necesario realizar ingeniería inversa a la función str_xor para este desafío.
## Solución 
Para la solución previa, cree un directorio con el nombre del nivel y descargue el archivo, para después verificar que si existe con ls
`resm-picoctf@webshell:~$ mkdir fixme2` 
`resm-picoctf@webshell:~$ cd fixme2/`
`resm-picoctf@webshell:~/fixme2$ wget https://artifacts.picoctf.net/c/4/fixme2.py`
`--2024-03-02 18:44:14--  https://artifacts.picoctf.net/c/4/fixme2.py`
`Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...`
`Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 1029 (1.0K) [application/octet-stream]`
`Saving to: 'fixme2.py'`

`fixme2.py                                       100%[======================================================================================================>]   1.00K  --.-KB/s    in 0s`      

`2024-03-02 18:44:14 (481 MB/s) - 'fixme2.py' saved [1029/1029]`

`resm-picoctf@webshell:~/fixme2$ ls`
`fixme2.py`

Aquí al momento de tratar de ejecutar el archivo me daba un error de igualdad, entonces corregí el codigo así:

`resm-picoctf@webshell:~/fixme2$ python fixme2.py` 
  `File "/home/resm-picoctf/fixme2/fixme2.py", line 22`
    `if flag = "":`
       `^^^^^^^^^`
`SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?`


`resm-picoctf@webshell:~/fixme2$ nano fixme2.py`
import random
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


`resm-picoctf@webshell:~/fixme2$ python fixme2.py`
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
resm-picoctf@webshell:~/fixme2$
## Contraseña obtenida 
picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
## Notas 
Es importante la sintaxis en un programa, ya que por ejemplo en python podemos descubrir que nuestra identación nuestra igualdad puede ser crucial a la hora de poder codificar algo, no solo en python si no también es importante saberlo en distintos lenguajes.

## Referencias 
https://datascientest.com/es/python-if-else#:~:text=%C2%BFQu%C3%A9%20es%20la%20sentencia%20If,si%20se%20cumple%20una%20condici%C3%B3n.
