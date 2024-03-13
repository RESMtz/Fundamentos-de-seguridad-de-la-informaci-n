## Descripción del reto
Hay algo en el edificio. ¿Puedes recuperar la bandera?
URL: https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
## Pistas 
Hay datos codificados en alguna parte... puede que haya un decodificador en línea
## Solución 
Hay dos maneras, la primera y más sencilla es el meter una imagen a un decodificador de esteganografia, la cual permite darnos accesso a la información solicitada.

La segunda manera es utilizando el zteg concatenando un grep, con la información de la flag.
Usaremos el comando 
zsteg -a buildings.jpg | grep picoCTF

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/What Lies Within]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2024-03-12 21:25:37--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                             100%[====================================================================================>] 610.57K  1.72MB/s    in 0.3s    

2024-03-12 21:25:38 (1.72 MB/s) - ‘buildings.png’ saved [625219/625219]

                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/What Lies Within]
└─$ sudo gem install zsteg                          
[sudo] password for kali: 
Fetching zpng-0.4.5.gem
Fetching rainbow-3.1.1.gem
Fetching zsteg-0.2.13.gem
Fetching iostruct-0.0.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.0.5
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.0.5
Installing ri documentation for iostruct-0.0.5
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 2 seconds
4 gems installed       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/What Lies Within]
└─$ zsteg -a buildings.jpg | grep picoCTF
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/What Lies Within]
└─$ zsteg -a buildings.png | grep picoCTF
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
## Contraseña obtenida 
picoCTF{h1d1ng_1n_th3_b1t5}
## Notas 
Obtuve un conocimiento más amplio sobre la esteganografia, la cual es un método bastante sútil de esconder datos, lo cual puede ser interesante y es una técnica que se puede aplicar de muchas maneras en contenido visual, que a no puede ser detectado tan fácilmente.
Sobre zsteg aprendí que también es un decodificador de esteganografía, que nos puede ser muy útil y más si trabajamos en consola.
## Referencias 
https://latam.kaspersky.com/resource-center/definitions/what-is-steganography