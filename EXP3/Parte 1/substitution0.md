## Descripción del reto
Ha llegado un mensaje pero parece estar todo codificado. Por suerte parece tener la clave al principio. ¿Puedes descifrar este cifrado de sustitución?
Descarga el mensaje [aquí](https://artifacts.picoctf.net/c/152/message.txt).
## Pistas 
Prueba un ataque de frecuencia. Una herramienta en línea podría ayudar.
## Solución 
Descargamos el archivo una vez descargado lo que podemos observar es un texto cifrado y lo introducimos a una herramienta online llamada [Substitution Solver](https://www.guballa.de/substitution-solver)
Una vez ahí introduccimos el texto y veremos que nos arroja lo siguiente: 
ABCDEFGHIJKLMNOPQRSTUVWXYZ 

Hereupon Legrand arose, with a grave and stately air, and brought me the beetle
from a glass case in which it was enclosed. It was a beautiful scarabaeus, and, at
that time, unknown to naturalists—of course a great prize in a scientific point
of view. There were two round black spots near one extremity of the back, and a
long one near the other. The scales were exceedingly hard and glossy, with all the
appearance of burnished gold. The weight of the insect was very remarkable, and,
taking all things into consideration, I could hardly blame Jupiter for his opinion
respecting it.

The flag is: picoCTF{5UB5717U710N_3V0LU710N_59533A2E}   


## Contraseña obtenida 
picoCTF{5UB5717U710N_3V0LU710N_59533A2E}   

## Notas 
Es importante saber auxiliarse de distintas herramientas online, para poder resolver nuestros problemas y poder obtener información decifrada a nuestros archivos.
## Referencias 
https://www.guballa.de/substitution-solver