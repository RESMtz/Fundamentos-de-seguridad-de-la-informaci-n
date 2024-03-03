## Descripción del reto
Hay un buen programa con el que puedes hablar usando este comando en un shell: $ nc mercury.picoctf.net 22342, pero no habla inglés...
## Pistas 
1.- Puedes practicar el uso de netcat con este problema de picoGym: ¿qué es un netcat?

2.- Puedes practicar la lectura y escritura en ASCII con este problema de picoGym: Vamos a calentar

## Solución 

1.- Este nivel es muy sencillo ya que simplemente basta con hacer nc, con los datos que nos permite el nivel en la descripción me apoye en la segunda pista con lo que nos arrojo, y después traducir este mensaje de ascii a texto:
resm-picoctf@webshell:~$  nc mercury.picoctf.net 22342
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
53 
102 
98 
53 
101 
53 
49 
100 
125 
10 
(Este mensaje lo traduce de ASCCI a texto )
picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}
## Contraseña obtenida 
picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}
## Notas 
Aquí me di cuenta de cuan importante es saber convertir nuestros números de ascii a texto, basta con simplemente buscar en un navegador o una imagen de la tabla ascii, es importante saber como hacer esto, ya que es una funcionalidad que nos permitira avanzar a otros niveles.
## Referencias 

Página de ASCII a texto
https://es.rakko.tools/tools/76/

