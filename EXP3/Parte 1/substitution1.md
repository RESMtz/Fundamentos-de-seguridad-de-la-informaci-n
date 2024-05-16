## Descripción del reto
Ha llegado un segundo mensaje por correo y parece casi idéntico al primero. Quizás vuelva a funcionar lo mismo.
Descarga el mensaje [aquí](https://artifacts.picoctf.net/c/183/message.txt).

## Pistas 
Prueba un ataque de frecuencia
¿La puntuación y las palabras individuales te ayudan a realizar alguna sustitución?
## Solución 
Como en el ejercicio anterior utilizamos una herramienta online, introducimos el texto y nos arroja lo siguiente: 
CTFs (short for capture the flag) are a type of computer security competition. Contestants are presented with a set of challenges which test their creativity, technical (and googling) skills, and problem-solving ability. Challenges usually cover a number of categories, and when solved, each yields a string (called a flag) which is submitted to an online scoring service. CTFs are a great way to learn a wide array of computer security skills in a safe, legal environment, and are hosted and played by many security groups around the world for fun and practice. For this problem, the flag is: picoCTF{FR3JU3NCY_4774CK5_4R3_C001_6E0659FB}

Aquí hicimos una corrección a la bandera de un caracter debido a que las herramientas online nos arroja la bandera y sustituimos por la correcta.

## Contraseña obtenida 
picoCTF{FR3QU3NCY_4774CK5_4R3_C001_6E0659FB}
## Notas 
Es importante saber utilizar herramientas que nos faciliten el hacer tareas complicadas como lo es aplicar el reversing y poder saber distinguir que herramientas son necesarias en cada ejercicio.
## Referencias 
https://www.guballa.de/substitution-solver
