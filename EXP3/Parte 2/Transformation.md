## Descripción del reto
Me pregunto qué es esto realmente... [enc](https://mercury.picoctf.net/static/e47483f88b12f2ab0c46315afc12f64d/enc) ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len( bandera), 2)])
## Pistas 
Puede encontrar algunos decodificadores en línea.
## Solución 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Transformation]
└─$ ls
enc
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Transformation]
└─$ cat enc          
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥ㄴㅡて㝽                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Transformation]
└─$ python3
`Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `enc=open("enc").read()`
>>> `print(enc)`
`灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥ㄴㅡて㝽`
>>> `print(hex(ord(enc[0])))`
`0x7069`
>>> `for c in enc:`
`... print(hex(ord(c)).lstrip("0x"),end='')`
  `File "<stdin>", line 2`
    `print(hex(ord(c)).lstrip("0x"),end='')`
    `^`
`IndentationError: expected an indented block after 'for' statement on line 1`
`>>> for c in enc:`
`... print(hex(ord(c)).lstrip("0x"),end='')`
  `File "<stdin>", line 2`
    `print(hex(ord(c)).lstrip("0x"),end='')`
    `^`
`IndentationError: expected an indented block after 'for' statement on line 1`
`>>> for c in enc:`
`...    print(hex(ord(c)).lstrip("0x"),end='')`
`...` 
`7069636f4354467b31365f626974735f696e73743334645f6f665f385f65313431613066377d>>>` 

Podemos ver que nos da una cadena de numeros.

## Contraseña obtenida 

## Notas 
Se va notando que la cadena va cambiando de un entero a un decimal, a hex para finalmente a codigo ascii, es importante saber estás conversiones ya que nos ayuda a realizar correctamente nuestras decodificaciones.
## Referencias 
https://www.rapidtables.com/convert/number/hex-to-ascii.html
