## Descripción del reto
¿Puedes conseguir la bandera?
Vaya a este sitio web y vea lo que puede descubrir.

## Pistas
¿Cómo se comprueba la contraseña en este sitio web?
## Solución 
Damos clic derecho y nuevamente inspeccionamos nuestra página web, pero este nivel no es parecido a los anteriores ya que si accedemos a una de las fuentes que estan ahí podemos ver que no genera gran cosa, entonces para ello me eh logeado con el nombre de un usuario aleatorio y una contraseña aleatoria, al momento de que volvemos a inspeccionar nos genera un script con el seguiente nombre secure.js el cual nos manda el siguiente código: 
`function checkPassword(username, password)`
`{`
  `if( username === 'admin' && password === 'strongPassword098765' )`
  `{`
    `return true;`
  `}`
  `else`
  `{`
    `return false;`
  `}`
`}`
Entonces aquí podemos obtener el nombre de usuario correcto con su password y al ingresar estos datos nos permite visualizar la bandera. 
## Contraseña obtenida 
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
## Notas 
Es necesario saber que acciones se ejecutan para llevar un muestreo como tal, esto con el fin de saber que acciones realizan cada cosa y además poder ayudarnos a saber que acciones y procesos hace al tratar de logear a un usuario. 
## Referencias 
No necesite referencias 
