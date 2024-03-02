## Descripción del reto
¿Podrás entrar en este portal súper seguro? https://jupiter.challenges.picoctf.org/problem/60786/ (enlace) o http://jupiter.challenges.picoctf.org:60786
## Pistas 
¿Qué es la ofuscación?
## Solución
Aquí accedemos al sitio como de costumbre, y al momento de nosotros poner, cualquier password que se nos venga a la mente no jala. Entonces para ello vamos a observar nuestro código fuente de la página el cual es el siguiente: 

`<html>`
`<head>`
`<title>Secure Login Portal V2.0</title>`
`</head>`
`<body background="[barbed_wire.jpeg](view-source:https://jupiter.challenges.picoctf.org/problem/60786/barbed_wire.jpeg)" >`
`<!-- standard MD5 implementation -->`
`<script type="text/javascript" src="[md5.js](view-source:https://jupiter.challenges.picoctf.org/problem/60786/md5.js)"></script>`

`<script type="text/javascript">`
  `var _0x5a46=['f49bf}','_again_e','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];(function(_0x4bd822,_0x2bd6f7){var _0xb4bdb3=function(_0x1d68f6){while(--_0x1d68f6){_0x4bd822['push'](_0x4bd822['shift']());}};_0xb4bdb3(++_0x2bd6f7);}(_0x5a46,0x1b3));var _0x4b5b=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x5a46[_0x2d8f05];return _0x4d74cb;};function verify(){checkpass=document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];split=0x4;if(checkpass[_0x4b5b('0x2')](0x0,split*0x2)==_0x4b5b('0x3')){if(checkpass[_0x4b5b('0x2')](0x7,0x9)=='{n'){if(checkpass[_0x4b5b('0x2')](split*0x2,split*0x2*0x2)==_0x4b5b('0x4')){if(checkpass[_0x4b5b('0x2')](0x3,0x6)=='oCT'){if(checkpass[_0x4b5b('0x2')](split*0x3*0x2,split*0x4*0x2)==_0x4b5b('0x5')){if(checkpass['substring'](0x6,0xb)=='F{not'){if(checkpass[_0x4b5b('0x2')](split*0x2*0x2,split*0x3*0x2)==_0x4b5b('0x6')){if(checkpass[_0x4b5b('0x2')](0xc,0x10)==_0x4b5b('0x7')){alert(_0x4b5b('0x8'));}}}}}}}}else{alert(_0x4b5b('0x9'));}}`
`</script>`
`<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:gray">`
`<div style="text-align:center">`
`<p>New and Improved Login</p>`

`<p>Enter valid credentials to proceed</p>`
`<form action="[index.html](view-source:https://jupiter.challenges.picoctf.org/problem/60786/index.html)" method="post">`
`<input type="password" id="pass" size="8" />`
`<br/>`
`<input type="submit" value="verify" onclick="verify(); return false;" />`
`</form>`
`</div>`
`</div>`
`</body>`
`</html>`
Podemos ver una linea que está ofuscada, esto quiere decir que tiene una tranformación de código a una versión mas segura. Ya que al ofuscarlo no es entendible.

Para desofuscarlo necesitamos del sitio jsnice lo introducimos y nos arroja lo siguiente: 
`/** @type {Array} */`
`var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];`
`(function(paths, opt_attributes) {`
  `/**`
   * `@param {number} val`
   * `@return {undefined}`
   `*/`
  `var setter = function(val) {`
    `for (;--val;) {`
      `paths["push"](paths["shift"]());`
    `}`
  `};`
  `setter(++opt_attributes);`
`})(_0x5a46, 435);`
`/**`
 * `@param {string} key`
 * `@param {?} dataAndEvents`
 * `@return {?}`
 `*/`
`var _0x4b5b = function(key, dataAndEvents) {`
  `/** @type {number} */`
  `key = key - 0;`
  `var label = _0x5a46[key];`
  `return label;`
`};`
`/**`
 * `@return {undefined}`
 `*/`
`function verify() {`
  `checkpass = document[_0x4b5b("0x0")]("pass")[_0x4b5b("0x1")];`
  `/** @type {number} */`
  `split = 4;`
  `if (checkpass[_0x4b5b("0x2")](0, split * 2) == _0x4b5b("0x3")) {`
    `if (checkpass[_0x4b5b("0x2")](7, 9) == "{n") {`
      `if (checkpass[_0x4b5b("0x2")](split * 2, split * 2 * 2) == _0x4b5b("0x4")) {`
        `if (checkpass[_0x4b5b("0x2")](3, 6) == "oCT") {`
          `if (checkpass[_0x4b5b("0x2")](split * 3 * 2, split * 4 * 2) == _0x4b5b("0x5")) {`
            `if (checkpass["substring"](6, 11) == "F{not") {`
              `if (checkpass[_0x4b5b("0x2")](split * 2 * 2, split * 3 * 2) == _0x4b5b("0x6")) {`
                `if (checkpass[_0x4b5b("0x2")](12, 16) == _0x4b5b("0x7")) {`
                  `alert(_0x4b5b("0x8"));`
                `}`
              `}`
            `}`
          `}`
        `}`
      `}`
    `}`
  `} else {`
    `alert(_0x4b5b("0x9"));`
  `}`
`}`
`;`

Podemos tomar la siguiente línea y pegarla en la consola de nuestro navegador:
`var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];`
![[Pasted image 20240302174314.png]]
Una vez ahí hacemos la concatenación del arreglo, de manera que nos quede una contraseña coherente y bien como voy a escribir a continuación:
'`_0x5a46[8] + _0x5a46[9] + _0x5a46[1] + _0x5a46[0]'
`"picoCTF{not_this_again_ef49bf}"`
Esta linea me permitio obtener la flag para completar nuestro nivel.



## Contraseña obtenida 
"picoCTF{not_this_again_ef49bf}"
## Notas 
La ofuscacion nos permite de manera segura poder cifrar el código de manera segura una página, en este nivel pude desarrollar un poco más mis habilidades respecto al tema, y sobre como se desempeña está función.
## Referencias
https://es.wikipedia.org/wiki/Ofuscaci%C3%B3n
