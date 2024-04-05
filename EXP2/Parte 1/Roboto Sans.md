## Descripción del reto
La bandera está en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntralo.
Mira esto.

## Pistas 
No hay pistas 
## Solución 
Primero que nada en el link original me guie por poner el robots.txt, el cual nos manda en pantalla lo siguiente: 
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
Este texto esta en base64 el cual decodificamos, y nos arroja la siguiente cadena:
js/myfile.txt

Ahora cambiamos el robots.txt por la cadena obtenida y finalmente obtenemos la flag.
## Contraseña obtenida 
picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}
## Notas 
Es importante saber manipular los enlaces, ya que de este modo nos ayuda a ser mas eficaces a la hora de poder obtener algun tipo de dato.

## Referencias 
https://www.base64decode.org/es/
