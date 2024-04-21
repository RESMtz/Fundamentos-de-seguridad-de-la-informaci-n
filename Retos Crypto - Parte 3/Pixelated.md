## Descripción del reto
Tengo estas 2 imágenes, ¿puedes hacer una bandera con ellas? revuelto1.png revuelto2.png
## Pistas 
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
Piense en diferentes formas de "apilar" imágenes
## Solución 
1. Descargar nuestra imagen en terminal con wget en nuestro directorio
2. Previamente descargando a grandes rasgos nos descarga unas imagenes que no nos proporciona gran información.
3. Luego de ahí tendremos que instalar una herramienta que nos ayude. 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Pixelated]
└─$ cd /opt                       
                                                                                                                                                                       
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar

--2024-04-20 19:44:01--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                             100%[====================================================================================>] 304.95K   188KB/s    in 1.6s    

2024-04-20 19:44:03 (188 KB/s) - ‘stegsolve.jar’ saved [312271/312271]
4. Despues aplicamos el siguiente comando para poder utilizar nuesta herrmienta:
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Pixelated]
└─$ java -jar /opt/stegsolve.jar 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

5. Una vez adentro en la herramienta damos clic en la esquina superior izquierda y abrimos la primer foto, una vez abierta ahora damos clic en Analyse y luego en image combiner para seleccionar la siguiente imagen.
6. Nos muestra una combinación que no muestra nada a simple vista, entonces le damos clic a la flecha con el simbolo > para ver los tipos de combinaciones diferentes, hasta que llegamos a una que dice ADD y nos da la flag
## Contraseña obtenida 
picoCTF{7188864c}
## Notas 
Podemos ver que nuestro sistema operativo cuenta con distintas herramientas de apoyo, para poder decifrar cientos de datos, que puede que desconozcamos que existian. 
## Referencias 
https://github.com/zardus/ctf-tools/blob/master/stegsolve/install

