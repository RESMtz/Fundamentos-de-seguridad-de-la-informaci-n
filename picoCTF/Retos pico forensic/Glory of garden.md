## Descripción del reto
Este jardín contiene más de lo que parece.
Url de la imagen: https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
## Pistas 
¿Qué es un editor hexadecimal?
## Solución 

Primero ingresamos a nuestra consola, cabe aclarar que se esta usando una consola del subsistema kali linux: 
1.- Nos ubicamos primeramente en nuestra carpeta donde está almacenada nuestra imagen:
┌──(kali㉿kali)-[~]
└─$ ls                     
Desktop    Downloads  Music     Public     Videos
Documents  hash       Pictures  Templates
                                                                             
┌──(kali㉿kali)-[~]
└─$ cd Desktop/Retos\ picoCTF/Retos\ forensic 
                                                                             
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic]
└─$ cd glory\ of\ the\ garden                
                                                                             
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/glory of the garden]
└─$ ls 
garden.jpg

2.- Una vez ahí abrimos el archivo, con el comando file solamente nos muestra de que tipo de archivo se trata:  
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/glory of the garden]
└─$ file garden.jpg 
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3

3.-Aquí hay dos soluciones podemos usar el hexeditor, en este comando se aplico eso mas las teclas CTRL+W la cual nos permite realizar una busqueda a través del archivo, una vez que nos pida que ingresemos el texto, ponemos nuestra flag picoCTF y encuentra esta cadena correctamente 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/glory of the garden]
└─$ hexeditor garden.jpg 
4.-O bien otra solución alternativa es usar el comando Strings, el cual nos permite extaer una cadena de dicho archivo, cabe aclarar que el -n nos sirve para poder limitar el número de caracteres en este caso fueron 13 y efectivamente nos arrojo la bandera 
 ┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/glory of the garden]
└─$ strings -n 13  garden.jpg                                 
Copyright (c) 1998 Hewlett-Packard Company
sRGB IEC61966-2.1
sRGB IEC61966-2.1
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
}>g<\gn_u5{4x
Y|Soif&YFQO=95
_c^mHEUUoy]]_F
ZRikwmum#|5iS
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/glory of the garden]
## Contraseña obtenida 
picoCTF{more_than_m33ts_the_3y33dd2eEF5}
## Notas 
Aquí pude darme cuenta de que utilidad y fin tiene el editor hexadecimal que es aquel programa que nos permite editar datos binarios de un archivo. Generalmente se hicieron para poder editar bloques que son hexadecimales, aquí solamente vi lo que viene siendo lo que contiene dentro un archivo lo que viene siendo jpg, que se compone de datos hexadeciamales, no tenía idea del tema y resulto bastante útil para la códificación y decodificacion dentro de estos archivos. Quien diría que podemos encontrar información tan interesante.
## Referencias 
https://es.wikipedia.org/wiki/Editor_hexadecimal
