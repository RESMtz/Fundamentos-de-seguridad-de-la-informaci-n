## Descripción del reto
Hay golpecitos provenientes de los cables. ¿Qué dice nc jupiter.challenges.picoctf.org 48247?
## Pistas 
¿Qué tipo de codificación utiliza guiones y puntos?
La bandera tiene el formato PICOCTF{}
## Solución 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ nc jupiter.challenges.picoctf.org 48247
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- } 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ nc jupiter.challenges.picoctf.org 48247 | xclip selection c
Command 'xclip' not found, but can be installed with:
sudo apt install xclip
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ sudo apt install xclip         
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  xclip
0 upgraded, 1 newly installed, 0 to remove and 433 not upgraded.
Need to get 21.3 kB of archives.
After this operation, 63.5 kB of additional disk space will be used.
Err:1 http://http.kali.org/kali kali-rolling/main amd64 xclip amd64 0.13-3
  404  Not Found [IP: 18.211.24.19 80]
E: Failed to fetch http://http.kali.org/kali/pool/main/x/xclip/xclip_0.13-3_amd64.deb  404  Not Found [IP: 18.211.24.19 80]
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ sudo apt update       
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 Packages [19.5 MB]
Get:3 http://kali.download/kali kali-rolling/main amd64 Contents (deb) [45.9 MB]
Get:4 http://kali.download/kali kali-rolling/contrib amd64 Packages [116 kB]                                                                                          
Get:5 http://kali.download/kali kali-rolling/contrib amd64 Contents (deb) [247 kB]                                                                                    
Get:6 http://kali.download/kali kali-rolling/non-free amd64 Packages [194 kB]                                                                                         
Get:7 http://kali.download/kali kali-rolling/non-free amd64 Contents (deb) [884 kB]                                                                                   
Get:8 http://kali.download/kali kali-rolling/non-free-firmware amd64 Packages [33.1 kB]                                                                               
Get:9 http://kali.download/kali kali-rolling/non-free-firmware amd64 Contents (deb) [16.9 kB]                                                                         
Fetched 66.9 MB in 26s (2,558 kB/s)                                                                                                                                   
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
570 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ sudo apt install xclip                                     
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  xclip
0 upgraded, 1 newly installed, 0 to remove and 570 not upgraded.
Need to get 21.3 kB of archives.
After this operation, 63.5 kB of additional disk space will be used.
Get:1 http://kali.download/kali kali-rolling/main amd64 xclip amd64 0.13-4 [21.3 kB]
Fetched 21.3 kB in 0s (45.4 kB/s) 
Selecting previously unselected package xclip.
(Reading database ... 404154 files and directories currently installed.)
Preparing to unpack .../xclip_0.13-4_amd64.deb ...
Unpacking xclip (0.13-4) ...
Setting up xclip (0.13-4) ...
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ nc jupiter.challenges.picoctf.org 48247 | xclip selection c
xclip: selection: No such file or directory
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ nc jupiter.challenges.picoctf.org 48247 | xclip -selection c 
Podemos ver que nuestro código es un código morse al momento de observar como si indican en las pistas, hay herramientas online que nos permiten decodificar nuestro mensaje. 


## Contraseña obtenida 
picoCTF{M0RS3C0D31SFUN1261438181}
## Notas 
El código morse ya lo conocía con anterioridad, nos puede ayudar en ciertas ocasiones tanto para poder cifrar como para poder decifrar. 
## Referencias 
https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4tLS0tIC4uLS0tIC0uLi4uIC4tLS0tIC4uLi4tIC4uLi0tIC0tLS4uIC4tLS0tIC0tLS4uIC4tLS0tIH0gDQo&ieol=CRLF