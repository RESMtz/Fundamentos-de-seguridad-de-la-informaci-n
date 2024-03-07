## Descripción del reto
Hay un sitio web en https://jupiter.challenges.picoctf.org/problem/52849/ (enlace). Alguien ha omitido el inicio de sesión antes y ahora se está fortaleciendo. ¡Intenta ver si aún puedes iniciar sesión! o http://jupiter.challenges.picoctf.org:52849

## Pistas 
The password is being filtered.
## Solución 
Usamos nuevamente la injection de sql, vamos a la pagina de login, vamos a inspector al campo de debug que colocamos en 1 y podemos ver la consulta. 
Pero en este nivel si nos detecta la injection del nivel anterior. 

Entonces optamos por el siguiente usuario:

username: admin';

Esta inyección nos permite delimitar los campos, como se aprecia es denotado por un ; para que se note:
password: admin
SQL query: SELECT * FROM users WHERE name='admin';' AND password='admin'

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}
## Contraseña obtenida 
picoCTF{m0R3_SQL_plz_fa983901}
## Notas 
Aprendí a usar otro tipo de inyección que me permite acceder.
## Referencias
https://www.w3schools.com/sql/sql_injection.asp
