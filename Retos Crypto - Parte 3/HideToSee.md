## Descripción del reto
¿Qué tal un poco de escondite, je?
Mira esta imagen aquí.
## Pistas 
Descarga la imagen e intenta extraerla.
## Solución 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/basic-mod1]
└─$ cd ..        
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ mkdir HideToSee                     
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ cd HideToSee 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/HideToSee]
└─$ wget https://artifacts.picoctf.net/c/240/atbash.jpg                                           
--2024-04-20 19:11:58--  https://artifacts.picoctf.net/c/240/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.11, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51508 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                                100%[====================================================================================>]  50.30K  --.-KB/s    in 0.07s   

2024-04-20 19:12:00 (744 KB/s) - ‘atbash.jpg’ saved [51508/51508]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/HideToSee]
└─$ ls
atbash.jpg
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/HideToSee]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_xz00558y}

-------------------------
Este último texto lo introducimos en el cyberchief para que nos pueda decifrar nuesta bandera
Lo metemos en cifrado de Atbash Cipher y nos arroja la contraseña

## Contraseña obtenida 
picoCTF{atbash_crack_ca00558b}
## Notas 
Es importante descubrir la variedad de como podemos obtener los datos, con los diferentes tipos de cifrado en este reto aprendí otro tipo de cifrado.
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfeHowMDU1OHl9DQo&ieol=CRLF&oeol=CRLF
https://byte-mind.net/oculta-tus-datos-una-imagen-steghide-kali-linux/
