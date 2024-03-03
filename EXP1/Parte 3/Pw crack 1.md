## Descripción del reto
¿Puedes descifrar la contraseña para obtener la bandera?
Descargue el verificador de contraseñas aquí y también necesitará la bandera cifrada en el mismo directorio.
## Pistas 
1.- Para ver el archivo en el webshell, haga: $ nano nivel1.py
2.-Para salir de nano, presione Ctrl y x y siga las instrucciones en pantalla.
3.- No es necesario realizar ingeniería inversa a la función str_xor para este desafío.

## Solución 
Para empezar cree mi directorio con el nombre del nivel, hice la descarga y comprobe con ls:
`resm-picoctf@webshell:~$ cd Pw-crack-1/`
`resm-picoctf@webshell:~/Pw-crack-1$ wget https://artifacts.picoctf.net/c/10/level1.py`
`--2024-03-02 18:53:29--  https://artifacts.picoctf.net/c/10/level1.py`
`Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.43, ...`
`Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 876 [application/octet-stream]`
`Saving to: 'level1.py'`

`level1.py                                       100%[======================================================================================================>]     876  --.-KB/s    in 0s`      

`2024-03-02 18:53:29 (394 MB/s) - 'level1.py' saved [876/876]`

`resm-picoctf@webshell:~/Pw-crack-1$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc`
`--2024-03-02 18:53:44--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc`
`Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.92, ...`
`Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 30 [application/octet-stream]`
`Saving to: 'level1.flag.txt.enc'`

`level1.flag.txt.enc                             100%[======================================================================================================>]      30  --.-KB/s    in 0s`      

`2024-03-02 18:53:44 (21.5 MB/s) - 'level1.flag.txt.enc' saved [30/30]`

`resm-picoctf@webshell:~/Pw-crack-1$ ls`
`level1.flag.txt.enc  level1.py`

Para ver el contenido del código, aplique nano. Lo cual fue importante, se puede ver en la línea que denote con muchos guiones, que hace una comparacion de la password.
`resm-picoctf@webshell:~/Pw-crack-1$ nano level1.py`
 THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
flag_enc = open('level1.flag.txt.enc', 'rb').read()
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"): --------------------------------------------------------
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")
level_1_pw_check()
Procedí a ejecutarlo y finalmente ingresar la contraseña que tenía dentro: 

resm-picoctf@webshell:~/Pw-crack-1$ python level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
## Contraseña obtenida 
picoCTF{545h_r1ng1ng_56891419}
## Notas 
Aquí simplemente aplique conocimientos previos a los que aplique en niveles anteriores.
## Referencias
En este caso no utilice referencias, ya que aplique comandos que eh visto repetidas veces