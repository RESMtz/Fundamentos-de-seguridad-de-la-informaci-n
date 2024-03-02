## Descripcion del reto
¿Puedes encontrar los robots?

`https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830
## Pistas
¿Qué parte del sitio web podría indicarte dónde el creador no quiere que mires?
## Solución 
Para empezar, tenemos que comenzar ingresando al sitio que se nos indica. Después investigamos en clase lo que viene siendo lo que es un archivo robots.txt y ver lo que es su defición y utilidad.
Insepeccionando el código fuente no nos da mucho, entonces comenzamos cambiando la dirección del sitio agregando al final la palabra "robots.txt". 
Entonces la liga queda así:
https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
Una vez ingresando ahí nos arroja las siguientes líneas:
User-agent: *
Disallow: /1bb4c.html
Podemos ver que hay una linea con extensión html:
Para ello reemplazamos la palbra robtos por lo que encontramos. 
https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html
Y nos manda al sitio de nuestra contraseña finalmente
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

## Contraseña obtenida para este nivel
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}
## Notas
Pude aprender lo que son los robots en una página html y en como funcionan. Pude comprender que son rasteardores y como por ejemplo en este nivel la descripción es que no quiere que el sitio no quiere que acceda, por lo tanto aplicamos está solución de ponerle al link nuestra extensión dando así el sitio donde no quiere que acceda. 
## Referencias 
https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es
