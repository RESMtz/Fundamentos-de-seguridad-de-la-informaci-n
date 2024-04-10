## Descripción del reto
Descifre este mensaje.

## Pistas 
tutorial de cifrado césar
## Solución 
Al descargar nuestro archivo podemos ver que si lo ejecutamos con un cat nos arroja un texto cifrado: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Actividad 14/caesar]
└─$ cat ciphertext.1
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}
Al momento de rotar nuestro texto en un decodificador online, me dio un texto coherente al rededor de las 48 rotaciones. 
En este caso lo hice mediante online, o elaboramos un archivo python. 
El código es el siguiente: 
  GNU nano 7.2                          exp.py                                   
import string 

import re 
abc=string.ascii_letters

encriptado= open('ciphertext' , 'r' ).read ()
encriptado=re.findall('\{(.*?)\}', encriptado)[0]
rot = 48
salida = ' '
for car in encriptado:
      salida += abc[ (abc.find(car)+ rot)%26  ]
print(salida)

## Contraseña obtenida 
picoCTF{crossingtherubicondjneoach}
## Notas 
A lo largo del tiempo es importante saber que tipo de cifrado conocemos, este caso en especifico es muy viejo. Pero es importante saber que se requiere para poder obtener información. 
## Referencias 
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,48)&input=Z3Zzd3dtcmt4bGl2eWZtZ3NyaG5yaXNlZ2w