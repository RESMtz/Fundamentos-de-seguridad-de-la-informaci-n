## Descripción del reto
¿Puedes descifrar este mensaje?
Descifre este [mensaje](https://artifacts.picoctf.net/c/159/cipher.txt) usando esta clave "CYLAB".
## Pistas 
https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución 
Descargamos el archivo y lo abrimos, a grandes razgos no vemos gran información. Pero mediante un decodificador online de vigenere podemos apoyarnos y le introducimos una llave la cual es CYLAB la cual nos puede ayudar 
─$ cat cipher.txt  
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}



## Contraseña obtenida 
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}
## Notas 
Es importante saber que factores se necesitan para poder usarlos, por ejemplo aquí se necesito de una llave y el texto cifrado, para poder realizarlo.
## Referencias 
https://www.boxentriq.com/code-breaking/vigenere-cipher