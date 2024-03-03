## Descripción del reto
¿Puedes descifrar la contraseña para obtener la bandera?
Descargue el verificador de contraseñas aquí y también necesitará la bandera cifrada en el mismo directorio.
## Pistas 
1.- ¿Te resulta familiar esa codificación?
2.- No es necesario realizar ingeniería inversa a la función str_xor para este desafío.

## Solución
resm-picoctf@webshell:~/Pw-crack-2$ ls
level2.flag.txt.enc  level2.py
resm-picoctf@webshell:~/Pw-crack-2$ nano level2.py
 `THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT` 


`########################`
`def str_xor(secret, key):`
    `#extend key to secret length`
    `new_key = key`
    `i = 0`
    `while len(new_key) < len(secret):`
        `new_key = new_key + key[i]`
        `i = (i + 1) % len(key)`        
    `return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])`
`###############################################################################`

`flag_enc = open('level2.flag.txt.enc', 'rb').read()`



`def level_2_pw_check():`
    `user_pw = input("Please enter correct password for flag: ")`
    `if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):`
        `print("Welcome back... your flag, user:")`
        `decryption = str_xor(flag_enc.decode(), user_pw)`
        `print(decryption)`
        `return`
    `print("That password is incorrect")`
`level_2_pw_check()`
Vemos aquí que nos deja esta línea en el condicional if:
user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65)
Entonces lo que hice fue convertir los valores hexadecimales en decimal y de ahí convertir los valores decimales a la tabla ASCCI
Una vez la conversión hecha ejecutamos el programa y de ahí nos pedira la contraseña que deciframos con los códigos:
resm-picoctf@webshell:~/Pw-crack-2$ python level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
## Contraseña obtenida 
picoCTF{tr45h_51ng1ng_502ec42e}
## Notas 
Aquí cabe recalcar que es importante saber analizar los archvios con el nano, además de saber decodificar, en este nivel fue muy interactivo ya que me ayudo a desarrollar un poco mejor lo que viene siendo el decodificar y saber ejectuar el nano para ver que se tiene dentro del archivo 
## Referencias 


Links:
https://masterplc.com/calculadora/hexadecimal-a-decimal/
https://elcodigoascii.com.ar/
