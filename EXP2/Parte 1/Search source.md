## Descripción del reto
El desarrollador de este sitio web dejó por error un artefacto importante en la fuente del sitio web, ¿puedes encontrarlo?
El sitio web está aquí
## Pistas 
¿Cómo podría reflejar el sitio web en su máquina local para poder utilizar herramientas de búsqueda más potentes?
## Solución 
─$ httrack http://saturn.picoctf.net:65086/
Mirror launched on Thu, 04 Apr 2024 04:46:58 by HTTrack Website Copier/3.49-5 [XR&CO'2014]
mirroring http://saturn.picoctf.net:65086/ with the wizard help..
* saturn.picoctf.net:65086/js/jquery.mCustomScrollbar.concat.min.js (45479 21/26: saturn.picoctf.net:65086/js/jquery.mCustomScrollbar.concat.min.js (0Done.: saturn.picoctf.net:65086/images/fevicon.png (153 bytes) - 404
Thanks for using HTTrack!
   
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt1/Search source ]
└─$ ls -l 
total 32
-rw-r--r-- 1 kali kali 4243 Apr  4 04:47 backblue.gif
-rw-r--r-- 1 kali kali  828 Apr  4 04:47 fade.gif
drwx------ 2 kali kali 4096 Apr  4 04:47 hts-cache
-rw-r--r-- 1 kali kali 1077 Apr  4 04:47 hts-log.txt
-rw-r--r-- 1 kali kali 5214 Apr  4 04:47 index.html
drwxr-xr-x 5 kali kali 4096 Apr  4 04:47 saturn.picoctf.net_65086
                                                                           
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt1/Search source ]
└─$ grep -nr "picoCTF"                              
saturn.picoctf.net_65086/css/style.css:328:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/

## Contraseña obtenida 
picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} 
## Notas 
Para ello acudí a buscar distintas herramientas en la web que nos pueden ayudar y desde la consola pude registrar el comando httrack el cual es un comando que nos permite visualizar nuestro sitio web deseado.
## Referencias 
https://es.wikipedia.org/wiki/HTTrack
https://www.um.es/docencia/barzana/SOFTWARE/Httrack-tutorial.php
