## Descripción del reto
El bloc de un solo uso puede ser criptográficamente seguro, pero no cuando se conoce la clave. ¿Puedes resolver esto? Le proporcionamos la bandera cifrada, la clave y una tabla para ayudar a UFJKXQZQUNB con la clave de SOLVECRYPTO. ¿Puedes utilizar esta tabla para resolverlo?.
## Pistas 
Envíe su respuesta en nuestro formato de bandera. Por ejemplo, si su respuesta fue "hola", enviaría "picoCTF{HELLO}" como bandera.

Utilice todas las mayúsculas para el mensaje.
## Solución 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14]
└─$ mkdir Easy1        
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14]
└─$ cd Easy1  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/Easy1]
└─$ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt      
--2024-04-10 04:00:53--  https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1571 (1.5K) [application/octet-stream]
Saving to: ‘table.txt’

table.txt                                 100%[===================================================================================>]   1.53K  --.-KB/s    in 0s      

2024-04-10 04:00:54 (23.8 MB/s) - ‘table.txt’ saved [1571/1571]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/Easy1]
└─$ ls
table.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/Easy1]
└─$ open table.txt      

Al abrir nuestro archivo de texto viene una tabla, la cual nos ayuda a poder resolver nuestra actividad, pero nuevamente nos apoyamos en nuestra herramienta cyber chief vemos que está códificado en vigenere decode lo podemos hacer manual o lo podemos hacer mediante cyber chief entonces yo opte por resolverlo manualmente.

## Contraseña obtenida 
picoCTF{CRYPTOISFUN}
## Notas 
Pude aprender a decodificar en vigenere, que es importante saber que herramientas se necesitan para poder realizar nuestra decodificación, la cual necesita de una llave y un mensaje cifrado. Es necesario apoyarse de estas dos herramientas, para poder decodificar. 
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI