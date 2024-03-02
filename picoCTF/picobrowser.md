## Descripción del reto
Este sitio web sólo puede ser renderizado por picobrowser, ¡ve y atrapa la bandera! https://jupiter.challenges.picoctf.org/problem/28921/ (enlace) o http://jupiter.challenges.picoctf.org:28921

## Pistas 
No es necesario descargar un nuevo navegador web
## Solución 
Comenzamos ingresando al sitio, pero nos llevamos una sorpresa al momento de ingresar con nuestro navegador convencional, no nos permite ver la bandera 
![[Pasted image 20240302170212.png]]
Entonces para ello accedemos de manera remota con nuestra consola, mediante el comando CURL y el sitio requerido para ello 
robert@DESKTOP-M9VOEL3:~$ curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser"
<!DOCTYPE html>
<html lang="en">

<head>
    <title>My New Website</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation" class="active"><a href="/">Home</a>
                    </li>
                    <li role="presentation"><a href="/unimplemented">Sign In</a>
                    </li>
                    <li role="presentation"><a href="/unimplemented">Sign Out</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">My New Website</h3>
        </div>

       <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->


       <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">
         <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
         <!-- <strong>Title</strong> --> picobrowser!
           </div>



        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
            <!-- <p><a class="btn btn-lg btn-success" href="admin" role="button">Click here for the flag!</a> -->
            <!-- </p> -->
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF 2019</p>
        </footer>

    </div>
    <script>
    $(document).ready(function(){
        $(".close").click(function(){
            $("myAlert").alert("close");
        });
    });
    </script>
</body>

</html>robert@DESKTOP-M9VOEL3:~$

`robert@DESKTOP-M9VOEL3:~$ curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser"`
`<!DOCTYPE html>`
`<html lang="en">`

`<head>`
    `<title>My New Website</title>`


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
                    `<li role="presentation" class="active"><a href="/">Home</a>`
                    `</li>`
                    `<li role="presentation"><a href="/unimplemented">Sign In</a>`
                    `</li>`
                    `<li role="presentation"><a href="/unimplemented">Sign Out</a>`
                    `</li>`
                `</ul>`
            `</nav>`
            `<h3 class="text-muted">My New Website</h3>`
        `</div>`

       `<!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->`


       `<div class="alert alert-success alert-dismissible" role="alert" id="myAlert">`
         `<button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>`
         `<!-- <strong>Title</strong> --> picobrowser!`
           `</div>`



        `<div class="jumbotron">`
            `<p class="lead"></p>`
            `<p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>`
            `<!-- <p><a class="btn btn-lg btn-success" href="admin" role="button">Click here for the flag!</a> -->`
            `<!-- </p> -->`
        `</div>`


        `<footer class="footer">`
            `<p>&copy; PicoCTF 2019</p>`
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

`</html>robert@DESKTOP-M9VOEL3:~$`

Se puede observar que pudimos obtener la flag mediante consola y el comando curl, 
picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}

## Contraseña obtenida 
picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}
## Notas 
Pude aprender en este nivel lo importante que es conocer quien o que es lo hacer mandar a llamar los distintos factores de nuestra red, por ejemplo aquí denotan quien es el que hace el request, y de que se encarga el User-Agent que es el que nos puede auxiliar a notificar al servidor desde donde se hace nuestra petición.
Además de que pude reforzar lo que viene siendo los conocimientos previos respecto a nuestro comando curl.
## Referencias 
https://developer.mozilla.org/es/docs/Web/HTTP/Headers/User-Agent
https://www.hostinger.mx/tutoriales/comando-curl

