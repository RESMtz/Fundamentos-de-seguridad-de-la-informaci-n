## Descripción del reto
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
Los números... ¿qué significan?
## Pistas 
La bandera tiene el formato PICOCTF{}
## Solución
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ mkdir "Actividad 14"                
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ cd Actividad\ 14 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14]
└─$ mkdir "The numbers" 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14]
└─$ cd The\ numbers 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/The numbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2024-04-10 03:45:19--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png                           100%[===================================================================================>]  98.36K  --.-KB/s    in 0.08s   

2024-04-10 03:45:19 (1.26 MB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/The numbers]
└─$ ls
the_numbers.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/The numbers]

Al abrir nuestra imagen vienen una serie de números que vienen codificados, el cual lo podemos solucionar al decodificar nuestros numeros en la página de cyber chief, entonces vamos y hacemos uso. 
picoctf␀thenumbersmason
Al hacer esto unicamente colocamos la bandera en formato adecuado.


## Contraseña obtenida 
picoCTF{thenumbersmason}

## Notas
Podemos hacer uso de diferentes cifrados, el cual es importante saber en que formato están cifradas las cosas para así poder obtener las herramientas adecuadas para poder obtener distintos datos.
## Referencias 
https://gchq.github.io/CyberChef/#recipe=A1Z26_Cipher_Decode('Space')&input=MTYgOSAzIDE1IDMgMjAgNiB7IDIwIDggNSAxNCAyMSAxMyAyIDUgMTggMTkgMTMgMSAxOSAxNSAxNH0
