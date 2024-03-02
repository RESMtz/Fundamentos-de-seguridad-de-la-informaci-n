## Descripción del reto

Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670

Kishor Balan nos advirtió que el siguiente código podría necesitar inspección: https://jupiter.challenges.picoctf.org/problem/9670/ (enlace) o http://jupiter.challenges.picoctf.org:9670
## Pistas 
1.- ¿Cómo se inspecciona el código web en un navegador?
2.- Hay 3 partes
## Solución 
1.- Comenzamos primeramente a inspeccionar la página con clic derecho y después en ver código fuente de la página nos arroja el siguiente sintaxis html:
`|   |`
`|---|`
`|<!doctype html>|`
`||<html>|`
`||<head>|`
`||<title>My First Website :)</title>|`
`||<link href="[https://fonts.googleapis.com/css?family=Open+Sans\|Roboto](https://fonts.googleapis.com/css?family=Open+Sans\|Roboto)" rel="stylesheet">|`
`||<link rel="stylesheet" type="text/css" href="[mycss.css](https://jupiter.challenges.picoctf.org/problem/9670/mycss.css)">|`
`||<script type="application/javascript" src="[myjs.js](https://jupiter.challenges.picoctf.org/problem/9670/myjs.js)"></script>|`
`||</head>|`
`|||`
`||<body>|`
`||<div class="container">|`
`||<header>|`
`||<h1>Inspect Me</h1>|`
`||</header>|`
`|||`
`||<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">What</button>|`
`||<button class="tablink" onclick="openTab('tababout', this, '#222')">How</button>|`
`|||`
`||<div id="tabintro" class="tabcontent">|`
`||<h3>What</h3>|`
`||<p>I made a website</p>|`
`||</div>|`
`|||`
`||<div id="tababout" class="tabcontent">|`
`||<h3>How</h3>|`
`||<p>I used these to make this site: <br/>|`
`||HTML <br/>|`
`||CSS <br/>|`
`||JS (JavaScript)|`
`||</p>|`
`||<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->|`
`||</div>|`
`|||`
`||</div>|`
`|||`
`||</body>|`
`||</html>|`
Podemos ver en una de las lineas que nos arroja una parte de la bandera la cual es:
picoCTF{tru3_d3

Después damos clic en la linea del archivo: 
link rel="stylesheet" type="text/css" href="[mycss.css](https://jupiter.challenges.picoctf.org/problem/9670/mycss.css)"
Y nos arroja lo siguiente: 
div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */

Aquí obtenemos la segunda parte de nuestro flag que es: 
Here's part 2/3 of the flag: t3ct1ve_0r_ju5t
Después salimos a la primera parte y entramos al otro archivo .js 
`<script type="application/javascript" src="[myjs.js](https://jupiter.challenges.picoctf.org/problem/9670/myjs.js)"></script>`
Que nos arroja lo siguiente:
Anyways part 3/3 of the flag: _lucky?2e7b23e3}

Finalmente concatenamos las 3 partes de la flag para  poder obtener nuestra contraseña: 
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
## Contraseña obtenida en este nivel 
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
## Notas 
Aquí pude aprender a inspeccionar páginas, que desde su código fuente puede ser útil, ejecutar lo que hay dentro de cada archivo.

## Referencias 
En este nivel no requerí sitios de terceros.