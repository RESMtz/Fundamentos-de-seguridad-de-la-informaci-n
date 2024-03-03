## Descripción del reto
¿Puedes descifrar la contraseña para obtener la bandera?
Descargue el verificador de contraseñas aquí y también necesitará la bandera cifrada y el hash en el mismo directorio.
Hay 7 contraseñas potenciales y 1 es correcta. Puede encontrarlos examinando el script de verificación de contraseñas.
## Pistas 
1.- Para ver el archivo nivel3.hash.bin en el webshell, haga: $ bvi nivel3.hash.bin

2.- Para salir de bvi escriba :q y presione enter.

3.- No es necesario realizar ingeniería inversa a la función str_xor para este desafío.
## Solución 
resm-picoctf@webshell:~/Pw-crack-3$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py
resm-picoctf@webshell:~/Pw-crack-3$ nano level3.py

`import hashlib`

THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT 
`def str_xor(secret, key):`
    `#extend key to secret length`
    `new_key = key`
    `i = 0`
    `while len(new_key) < len(secret):`
        `new_key = new_key + key[i]`
        `i = (i + 1) % len(key)`        
    `return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])`
`###############################################################################`

`flag_enc = open('level3.flag.txt.enc', 'rb').read()`
`correct_pw_hash = open('level3.hash.bin', 'rb').read()`


`def hash_pw(pw_str):`
    `pw_bytes = bytearray()`
    `pw_bytes.extend(pw_str.encode())`
    `m = hashlib.md5()`
    `m.update(pw_bytes)`
    `return m.digest()`


`def level_3_pw_check():`
    `user_pw = input("Please enter correct password for flag: ")`
    `user_pw_hash = hash_pw(user_pw)`
    
    `if( user_pw_hash == correct_pw_hash ):`
        `print("Welcome back... your flag, user:")`
        `decryption = str_xor(flag_enc.decode(), user_pw)`
        `print(decryption)`
        `return`
    `print("That password is incorrect")`
    


`level_3_pw_check()`


`The strings below are 7 possibilities for the correct password.` 
   `(Only 1 is correct)`
`pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]`

Aquí fuí probando la lista de posibles combinaciones que tenemos en nuestro archivo hasta que finalmente encontre la combinación correcta:
resm-picoctf@webshell:~/Pw-crack-3$ python level3.py 
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
## Contraseña obtenida 
picoCTF{m45h_fl1ng1ng_2b072a90}
## Notas 
## Referencias 
