## Descripción del reto
Los atacantes han ocultado información en una gran masa de datos en el pasado, tal vez todavía lo estén haciendo.
Descarga los datos aquí.

## Pistas 
Descargue el archivo y busque la bandera según el prefijo conocido.
## Solución 
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Lookey here]
└─$ wget https://artifacts.picoctf.net/c/125/anthem.flag.txt       
--2024-04-04 18:10:14--  https://artifacts.picoctf.net/c/125/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt                           100%[====================================================================================>] 106.12K  --.-KB/s    in 0.1s    

2024-04-04 18:10:15 (1017 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Lookey here]
└─$ file anthem.flag.txt                  
anthem.flag.txt: Unicode text, UTF-8 text
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Lookey here]
└─$ open anthem.flag.txt       
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Lookey here]
└─$ grep "picoCTF" athem.flag.txt


grep: athem.flag.txt: No such file or directory
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Lookey here]
└─$ grep "picoCTF" anthem.flag.txt 


      we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
## Contraseña obtenida
picoCTF{gr3p_15_@w3s0m3_58f5c024}
## Notas 
Es importante saber que en un archivo de texto el uso del comando Grep podemos facilitar la busqueda de determinada cadena, es un comando muy útil que nos basta con saber escribir la sintaxis correcta. 
## Referencias 
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.
