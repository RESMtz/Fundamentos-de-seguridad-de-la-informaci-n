## Descripción del reto
Hay un sitio web en https://jupiter.challenges.picoctf.org/problem/39720/ o http://jupiter.challenges.picoctf.org:39720. ¿Crees que puedes iniciar sesión con nosotros? ¡Intenta ver si puedes iniciar sesión!


## Pistas
1.- No parece haber muchas formas de interactuar con esto. Me pregunto si los usuarios se mantienen en una base de datos.

2.- Intente pensar en cómo el sitio web verifica su inicio de sesión. 
## Solución 
Para este nivel usamos SQL injection, para poder comprobar un condicional que nos ayuda a podernos logear, primero ingresamos como usuario normal, pero la página genera un error, checamos en el código de la fuente de la página. 

Vamos al inspector del navegador, luego vamos a selecionar el campo de la contraseña. Hay un valor en debug, este valor lo ponemos en 1. Es un query en la que se valida el usuario.

La inyección nos queda del siguiente modo
username: ' or 1=1;
password: password (Esta password fue propuesta por mi)
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='password'

 
 Logged in!

Your flag is: picoCTF{s0m3_SQL_c218b685}
## Contraseña obtenida 
picoCTF{s0m3_SQL_c218b685}
## Notas 
Aquí pude desempeñar el uso de la inyección sql, la cual por medio de una query nos permite validar lo que viene siendo una condición en el usuario y así darnos permisos del administrador.

## Referencias 
https://www.w3schools.com/sql/sql_injection.asp