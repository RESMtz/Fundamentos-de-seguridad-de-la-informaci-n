## Descripción del reto
La fábrica oculta cosas a todos sus usuarios. ¿Puedes iniciar sesión como Joe y encontrar lo que han estado mirando? https://jupiter.challenges.picoctf.org/problem/44573/ (enlace) o http://jupiter.challenges.picoctf.org:44573
## Pistas 
Hmm, ¿no parece verificar la contraseña de nadie, excepto la de Joe?
## Solución 
Primeramente, ingresamos al sitio para ver que es lo que sucede si entramos con usuario de Joe:
![[Pasted image 20240302161732.png]]
Vemos que nos coloca lo que viene siendo un mensaje diciendo que la contraseña de Joe es super segura.
Entonces probamos con otro usuario:
![[Pasted image 20240302161853.png]]
Al momento de ingresar otro usuario podemos observar que si se logea, pero no nos deja ver la bandera. Entonces para ello vemos las cookies del sitio a la hora de ingresar. 

![[Pasted image 20240302162202.png]]
Se observa que la bandera del usuario esta en False entonces para poder solucionar este problema mediante la extensión cookie editor haremos esto.

Una vez descargada e instalada nuestra extensión nos logeamos nuevamente para poder ver mediante el editor que es lo que pasa: 
![[Pasted image 20240302162806.png]]
Una vez ahí el valor que está en el campo de Value, lo cambiamos por True
Y finalmente nos arroja nuestra contraseña:
![[Pasted image 20240302162927.png]]
## Contraseña obtenida 
picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}
## Notas 
En este trabajo pude comprender mucho mejor lo que vienen siendo las cookies, lo cual son pequeños bloques que almacenan información de los sitios, además que también pude comprender mucho mejor lo que vienen siendo nuestro protocolo HTML, información de la cual no tenía conocimiento. 
## Referencias 
https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/HTML_basics
https://www.kaspersky.es/resource-center/definitions/cookies


