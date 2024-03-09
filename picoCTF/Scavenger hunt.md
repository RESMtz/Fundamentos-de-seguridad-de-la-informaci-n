## Descripción del reto
Hay información interesante escondida en este sitio http://mercury.picoctf.net:27393/. ¿Puedes encontrarlo?
## Pistas 
Deberías tener suficientes pistas para encontrar los archivos, no ejecutes fuerza bruta.
## Solución 
1.- Primero ingresamos al sitio que se nos pide, para luego darle clic derecho y ver el código fuente de la página el cual es el siguiente:
`<!doctype html>`
`<html>`
  `<head>`
    `<title>Scavenger Hunt</title>`
    `<link href="[https://fonts.googleapis.com/css?family=Open+Sans|Roboto](view-source:https://fonts.googleapis.com/css?family=Open+Sans|Roboto)" rel="stylesheet">`
    `<link rel="stylesheet" type="text/css" href="[mycss.css](view-source:http://mercury.picoctf.net:27393/mycss.css)">`
    `<script type="application/javascript" src="[myjs.js](view-source:http://mercury.picoctf.net:27393/myjs.js)"></script>`
  `</head>`

  `<body>`
    `<div class="container">`
      `<header>`
		`<h1>Just some boring HTML</h1>`
      `</header>`

      `<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>`
      `<button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>`

      `<div id="tabintro" class="tabcontent">`
		`<h3>How</h3>`
		`<p>How do you like my website?</p>`
      `</div>`

      `<div id="tababout" class="tabcontent">`
		`<h3>What</h3>`
		`<p>I used these to make this site: <br/>`
		  `HTML <br/>`
		  `CSS <br/>`
		  `JS (JavaScript)`
		`</p>`
	# <font style="color:green">!-- Here's the first part of the flag: picoCTF{t --</font>
	
      `</div>`

    `</div>`

  `</body>`
`</html>`
Como se ve en las últimas lineas nos indica donde está nuestra primera parte del flag: aquí la línea   <font style="color:red">!-- Here's the first part of the flag: picoCTF{t --</font>
2.- Ahora dentro de este mismo código HTML de la página damos clic en el archivo java script llamado: 
<font style="color:purple">"mycss.css"> --</font>
Accediendo nos arroja el siguiente código: 
`div.container {`
    `width: 100%;`
`}`

`header {`
    `background-color: black;`
    `padding: 1em;`
    `color: white;`
    `clear: left;`
    `text-align: center;`
`}`

`body {`
    `font-family: Roboto;`
`}`

`h1 {`
    `color: white;`
`}`

`p {`
    `font-family: "Open Sans";`
`}`

`.tablink {`
    `background-color: #555;`
    `color: white;`
    `float: left;`
    `border: none;`
    `outline: none;`
    `cursor: pointer;`
    `padding: 14px 16px;`
    `font-size: 17px;`
    `width: 50%;`
`}`

`.tablink:hover {`
    `background-color: #777;`
`}`

`.tabcontent {`
    `color: #111;`
    `display: none;`
    `padding: 50px;`
    `text-align: center;`
`}`

`#tabintro { background-color: #ccc; }`
`#tababout { background-color: #ccc; }`

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

Como se observa en la última línea nos arroja la siguiente parte del flag: 
<font style="color:red">/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */{t --</font>
3.- Ahora si entramos al siguiente archivo .css nos da la siguiente pista: 
`function openTab(tabName,elmnt,color) {`
    `var i, tabcontent, tablinks;`
    `tabcontent = document.getElementsByClassName("tabcontent");`
    `for (i = 0; i < tabcontent.length; i++) {`
	`tabcontent[i].style.display = "none";`
    `}`
    `tablinks = document.getElementsByClassName("tablink");`
    `for (i = 0; i < tablinks.length; i++) {`
	`tablinks[i].style.backgroundColor = "";`
    `}`
    `document.getElementById(tabName).style.display = "block";`
    `if(elmnt.style != null) {`
	`elmnt.style.backgroundColor = color;`
    `}`
`}`

`window.onload = function() {`
    `openTab('tabintro', this, '#222');`
`}`

`/* How can I keep Google from indexing my website? */`

La última linea hace referencia a lo visto en clase, en como se mantiene indexada la página, pues es muy sencillo con el archivo robots.txt es la solución, para ello modificamos nuestro link añadiendo la extensión robots.txt :
http://mercury.picoctf.net:27393/robots.txt
Una vez ahí nos arroja la siguiente parte de la flag: 
<font style="color:red"># Part 3: t_0f_pl4c</font>
4.- Ahora para la siguiente parte necesitamos otro tipo de extensión en la página el cual es .htaccess, el cual nos permite es un fichero de texto plano que se emplea para configurar determinados aspectos de tu web :
http://mercury.picoctf.net:27393/.htaccess
<font style="color:red"># Part 4: 3s_2_lO0k</font>
5.- Finalmente, accedemos al sitio modificando una vez el link original, el cual nos permite usar las distintas opciones de visualización:

http://mercury.picoctf.net:27393/.DS_Store
<font style="color:red">Part 5: _d375c750}</font>


## Contraseña obtenida 
  <font style="color:red">picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k _d375c750}</font>
  
  

## Notas 
Aquí aprendí el uso de los archivos y para que sirven cada uno de ellos lo que vienen siendo el .htaccess y DS_Store los cuales desepeñan funciones totalmente distintas.
## Referencias 
https://support.microsoft.com/es-es/office/quitar-ds-store-archivos-en-macos-d2f8dca0-740a-4f7e-89b9-5b2cbbc50386#:~:text=DS_Store%20archivos%20para%20almacenar%20opciones,da%C3%B1ado%2C%20tendr%C3%A1%20que%20usar%20terminal.
https://es.semrush.com/blog/archivo-htaccess/

