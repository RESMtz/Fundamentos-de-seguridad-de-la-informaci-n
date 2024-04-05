## Descripción del reto
¿Puedes encontrar la bandera? shark1.pcapng.

## Pistas 
No hay
## Solución 
1.- Descargamos la captura y la colocamos en nuestro directorio. 
2.- Basta con dar clic al primer dato, clic derecho y luego a follow.
3.- A simple vista no nos arroja nada, pero conforme avanzamos de paquete en mi caso fue hasta el 5 nos arroja algo más legible.
4.- Una vez ahí la última linea nos parece familiar a un formato antes trabajado, entonces vemos que está en ROT13, de está manera nos damos cuenta que podemos decodificarla.
5.- cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
Una vez decodificada, finalmente nos da la flag 
## Contraseña obtenida 
picoCTF{p33kab00_1_s33_u_deadbeef}
## Notas 
Es importante saber en que formato están codificadas las cosas en cualquier archivo ya que de esta manera podemos identificar nuestras herramientas y podemos plantear mucho mejor nuestra manera de obtener datos y decodificar las cosas. 
## Referencias 
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)ROT13(true,true,false,13)ROT13(true,true,false,13)&input=Y3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQ&ieol=CRLF&oeol=CRLF
