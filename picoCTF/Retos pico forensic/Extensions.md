## Descripción del reto
¿Este es un archivo de texto TXT realmente extraño? ¿Puedes encontrar la bandera?
URL del archivo: https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
## Pistas
1.- ¿Cómo saben los sistemas operativos qué tipo de archivo es? (¡No es sólo el final!
2.- Make sure to submit the flag as picoCTF{XXXXX}
## Solución
Ubicamos nuestro archivo, pero la sorpresa es que viene el archivo en formato txt, pero cuando vemos de que tipo de archivo se trata, vemos que nuestro archivo, es un PNG o igual si vemos desde el hex editor podemos ver la referencia a la firma |`89 50 4E 47 0D 0A 1A 0A`| la cual nos indica que es un archivo png. 
──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ file flag.txt  
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ hexeditor flag.txt  

Entonces como nuestro archivo es TXT mediante el comando mv lo usamos para poder cambiar el tipo de archivo que es y acomodarlo como está: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ mv flag.txt flag.png

Una vez ahí obtenemos nuestro archivo ya cambiado lo abrimos y nos arroja el flag 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ ls
flag.png

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ open flag.png  

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/Extensions]
└─$ open flag.png
 


## Contraseña obtenida 
picoCTF{now_you_know_about_extensions}
## Notas 
Aquí pude ver cuan importante es saber analizar las firmas de nuestros archivos, ya que por ejemplo en este ejercicio si aplicamos un cat nos arroja una cantidad rara de valores y caracteres que no podemos entender, entonces si realizamos el cambio a un archivo png nos permitirá manipular el archivo, pero no necesariamente podemos convetir unicamente a pdf, también a otro tipo de archivos.
## Referencias 
https://schulich.libguides.com/c.php?g=721481&p=5159438#:~:text=mv%20is%20used%20to%20move,new%20name%20as%20shown%20below.
https://en.wikipedia.org/wiki/List_of_file_signatures

