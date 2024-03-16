

## Descripción del reto
Dejé de usar YellowPages y pasé a WhitePages... ¡pero la página que me dieron está toda en blanco!
## Pistas 
-
## Solución 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/WhitePages]
└─$ wget https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt
--2024-03-15 23:59:52--  https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2976 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt                            100%[===================================================================================>]   2.91K  --.-KB/s    in 0s      

2024-03-15 23:59:52 (49.2 MB/s) - ‘whitepages.txt’ saved [2976/2976]

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/WhitePages]
└─$ ls
whitepages.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/WhitePages]
└─$ ls -la                 
total 12
drwxr-xr-x 2 kali kali 4096 Mar 15 23:59 .
drwxr-xr-x 9 kali kali 4096 Mar 15 23:59 ..
-rw-r--r-- 1 kali kali 2976 Oct 26  2020 whitepages.txt

codigo nano exp.py

from pwn import * 

file = open ('whitepages.txt','rb' )
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)
print(data)

`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/WhitePages]`
`└─$ python exp.py`
`b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'`

## Contraseña obtenida 
picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}
## Notas 
Pude obtener la password por medio de la manipulación del python, pero también es importante saber el proceso de nuestro programa que se hizo la conversion de binario a caracter.
## Referencias 
https://parzibyte.me/blog/2021/03/11/python-traductor-binario-texto/

