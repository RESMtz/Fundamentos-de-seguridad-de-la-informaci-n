
## Descripción del reto
Para obtener realmente 1337, debes comprender diferentes codificaciones de datos, como hexadecimal o binaria. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conéctese con nc jupiter.challenges.picoctf.org 29956.
## Pistas 
1.- Escuché que Python puede convertir cosas.
2.- Puede resultar útil tener varias ventanas abiertas.
## Solución 
resm-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
container
Please give the 01100011 01101111 01101110 01110100 01100001 01101001 01101110 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
container
Please give me the  146 141 154 143 157 156 as a word.
Input:
falcon
Please give me the 7375626d6172696e65 as a word.
Input:
submarine
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

Primero usamos una conversión de binario a código asscci 

Despues una de octal a Ascii

Luego una de hexa a Ascii
## Contraseña obtenida 
## Notas 
Aquí cabe recalcar que preferí agilizar la conversión con herrmientas en línea
## Referencias 
https://www.calculadoraconversor.com/binario-a-ascii/#fbuilder
https://onlinetools.com/ascii/convert-octal-to-ascii
https://www.rapidtables.com/convert/number/hex-to-ascii.html
