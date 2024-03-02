## Descripción del reto
¿Podrás entrar en este portal súper seguro? https://jupiter.challenges.picoctf.org/problem/17682/ (enlace) o http://jupiter.challenges.picoctf.org:17682
## Pistas 
Nunca confíes en el cliente
## Solución 
Al momento de tratar de ingresar con un password este nos marca lo que viene que es incorrecto, entonces, inspeccionando la página podemos observar que la parte del servidor nos deja acceder al script de la página.
![[Pasted image 20240302164525.png]]
Para posteriormente acceder al script nos colocamos en el apartado de depurador y tendremos accceso al script, el cual nos arroja el siguiente código: 
`<html>`
`<head>`
`<title>Secure Login Portal</title>`
`</head>`
`<body bgcolor=blue>`
`<!-- standard MD5 implementation -->`
`<script type="text/javascript" src="md5.js"></script>`

`<script type="text/javascript">`
  `function verify() {`
    `checkpass = document.getElementById("pass").value;`
    `split = 4;`
    `if (checkpass.substring(0, split) == 'pico') {`
      `if (checkpass.substring(split*6, split*7) == '706c') {`
        `if (checkpass.substring(split, split*2) == 'CTF{') {`
         `if (checkpass.substring(split*4, split*5) == 'ts_p') {`
          `if (checkpass.substring(split*3, split*4) == 'lien') {`
            `if (checkpass.substring(split*5, split*6) == 'lz_b') {`
              `if (checkpass.substring(split*2, split*3) == 'no_c') {`
                `if (checkpass.substring(split*7, split*8) == '5}') {`
                  `alert("Password Verified")`
                  `}`
                `}`
              `}`
      
            `}`
          `}`
        `}`
      `}`
    `}`
    `else {`
      `alert("Incorrect password");`
    `}`
    
  `}`
`</script>`
`<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:yellow">`
`<div style="text-align:center">`
`<p>This is the secure login portal</p>`
`<p>Enter valid credentials to proceed</p>`
`<form action="index.html" method="post">`
`<input type="password" id="pass" size="8" />`
`<br/>`
`<input type="submit" value="verify" onclick="verify(); return false;" />`
`</form>`
`</div>`
`</div>`
`</body>`
`</html>`
Podemos ver que hay un serie de if´s anidados los cuales van haciendo una serie de comparaciones para poder verificar que la constraseña es correcta, entonces para poder decifrar lo que viene siendo la solución de este nivel concatenamos los if por orden númerico 
Y nos quedaría así:
`if (checkpass.substring(0, split) == 'pico') {`
`if (checkpass.substring(split, split*2) == 'CTF{') {`
`if (checkpass.substring(split*2, split*3) == 'no_c') {`
`if (checkpass.substring(split*3, split*4) == 'lien') {`
`if (checkpass.substring(split*4, split*5) == 'ts_p') {`
`if (checkpass.substring(split*5, split*6) == 'lz_b') {`
`if (checkpass.substring(split*6, split*7) == '706c') {`
`if (checkpass.substring(split*7, split*8) == '5}') {`
Aquí acomodados esta serie de condicionales if, formamos la contraseña adecuada:
picoCTF{no_clients_plz_b706c5}
    
## Contraseña obtenida 
picoCTF{no_clients_plz_b706c5}

## Notas 
Aquí este nivel es con intención de que a la hora de que programamos un sitio web, es importante saber en que lugar dejamos las cosas, porque si dejamos a simple vista algo tan importante como lo es el código del sitio web, puede que presentemos problemas y nos despojen los datos como lo son, contraseñas y datos del sitio web.

## Referencias 
https://www.cloudflare.com/es-es/learning/serverless/glossary/client-side-vs-server-side/
