## Descripción del reto
A veces es necesario manejar datos de proceso fuera de un archivo. ¿Puedes encontrar una manera de conservar el resultado de este programa y buscar la bandera? Conéctese a jupiter.challenges.picoctf.org 4427.
## Pistas 
1.- Recuerde que el formato de la bandera es picoCTF{XXXX}
2.- ¿Qué es una pipa? No, no ese tipo de pipa... Este tipo [pipa](http://www.linfo.org/pipes.html)
## Solución 
resm-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 | grep picoCTF     
picoCTF{digital_plumb3r_5ea1fbd7}

Solamente usamos la pipa para concatenar con un grep y extraer de las lineas la flag con picoCTF de las lineas
## Contraseña obtenida 
picoCTF{digital_plumb3r_5ea1fbd7}
## Notas 
Es importante saber concatenar dos comandos, ya que de esa manera nos facilita muchas más tareas.
## Referencias 
https://www.ionos.mx/digitalguide/servidores/configuracion/pipes-linux/



