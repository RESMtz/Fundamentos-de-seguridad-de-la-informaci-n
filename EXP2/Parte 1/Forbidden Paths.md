## Descripción del reto
¿Puedes conseguir la bandera?
Aquí está el sitio web.
Sabemos que los archivos del sitio web se encuentran en /usr/share/nginx/html/ y la bandera está en /flag.txt, pero el sitio web está filtrando rutas absolutas de archivos. ¿Puedes pasar el filtro para leer la bandera?
## Pistas 
No hay 
## Solución 
Para ello hay un buscador de archivos, entonces se nos da la indicacion que la flag está despues de ciertos directorios, entonces para ello usamos "../" para poder saltar en jerarquía de directorios. El cual nos permite si por ejemplo se nos indica que son 5 directorios entonces pondremos en la barra ../../../../../flag.txt el cual nos permitira visualizar la bandera.
## Contraseña obtenida
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}
## Notas 
Se requiere saber manipular directorios para poder realizar una busqueda de cierto elemento indicado.
## Referencias 
https://keepcoding.io/blog/estructura-de-directorios/#:~:text=el%20desarrollo%20web!-,%C2%BFQu%C3%A9%20es%20la%20estructura%20de%20directorios%3F,archivos%20almacenados%20en%20el%20sistema.
