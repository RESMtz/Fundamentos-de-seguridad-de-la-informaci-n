## Descripción del reto
Encuentra la bandera que se mantiene en este servidor para adelantarte a la competencia http://mercury.picoctf.net:15931/
## Pistas 
1.- Quizás tengas más de 2 opciones.
2.- Consulte herramientas como Burpsuite para modificar sus solicitudes y observar las respuestas.
## Solución 
Aplicamos un CURL con -X para poder observar, el -X nos permite hacer el tipo de solicitud que permite usar el POST: 
robert@DESKTOP-M9VOEL3:~$ curl -X POST http://mercury.picoctf.net:15931/index.php?

`<!doctype html>`
`<html>`
`<head>`
    `<title>Blue</title>`
    `<link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">`
        `<style>body {background-color: blue;}</style>`
`</head>`
        `<body>`
                `<div class="container">`
                        `<div class="row">`
                                `<div class="col-md-6">`
                                        `<div class="panel panel-primary" style="margin-top:50px">`
                                                `<div class="panel-heading">`
                                                        `<h3 class="panel-title" style="color:red">Red</h3>`
                                                `</div>`
                                                `<div class="panel-body">`
                                                        `<form action="index.php" method="GET">`
                                                                `<input type="submit" value="Choose Red"/>`
                                                        `</form>`
                                                `</div>`
                                        `</div>`
                                `</div>`
                                `<div class="col-md-6">`
                                        `<div class="panel panel-primary" style="margin-top:50px">`
                                                `<div class="panel-heading">`
                                                        `<h3 class="panel-title" style="color:blue">Blue</h3>`
                                                `</div>`
                                                `<div class="panel-body">`
                                                        `<form action="index.php" method="POST">`
                                                                `<input type="submit" value="Choose Blue"/>`
                                                        `</form>`
                                                `</div>`
                                        `</div>`
                                `</div>`
                        `</div>`
                `</div>`
        `</body>`
`</html>`


Ahora bien una vez que corroboramos el tipo de solicitud que -I se refiere al HEAD de la página:  
`robert@DESKTOP-M9VOEL3:~$ curl -I HEAD http://mercury.picoctf.net:15931/index.php?`
`curl: (6) Could not resolve host: HEAD`
`HTTP/1.1 200 OK`
`flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}`
`Content-type: text/html; charset=UTF-8`
Y se observa que el envío de la solicitud fue exitoso y nos arroja la bandera. 

## Contraseña obtenida 
picoCTF{r3j3ct_th3_du4l1ty_82880908}
## Notas 
Aprendí el uso y diferenciar para que nos sirve cada solicitud, como se observa en la parte de arriba.
## Referencias 
https://www.godaddy.com/resources/latam/stories/que-es-comando-curl-como-usarlo
https://www.hostinger.mx/tutoriales/bash-for-loop-guia-ejemplos
