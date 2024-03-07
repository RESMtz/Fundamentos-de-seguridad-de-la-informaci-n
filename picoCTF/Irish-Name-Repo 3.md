## Descripción del reto
Hay un sitio web seguro en https://jupiter.challenges.picoctf.org/problem/29132/ (enlace) o http://jupiter.challenges.picoctf.org:29132. ¡Intenta ver si puedes iniciar sesión como administrador!
## Pistas 
Seems like the password is encrypted.
## Solución 
Aquí en el login se nos pide unicamente una contraseña, si nostros ponemos en prática lo del nivel anterior entonces probamos con lo siguiente: 
password: ' or 1=1;

Nos arroja la siguiente: 
SQL query: SELECT * FROM admin where password = ''be1=1;'

Entonces acudimos al ciber chief 
Al traducir lo siguiente en formato ROT13 nos ayuda a la obtención de nuestra bandera:

Entonces esto lo introducimos nuevamente a nuestro campo de password 

Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}
## Contraseña obtenida 
picoCTF{3v3n_m0r3_SQL_06a9db19}
## Notas 
Aquí pude diferenciar entre las distintas inyecciones que nos pueden ayudar a generar o decifrar distintas contraseñas 

## Referencias 
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBiZSAxPTE7
https://www.w3schools.com/sql/sql_injection.asp
