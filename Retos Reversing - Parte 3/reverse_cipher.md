## Descripción del reto
Hemos recuperado un archivo [binario](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) y uno de [texto](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). ¿Puedes invertir la bandera?
## Pistas 
objdump y Gihdra son algunas herramientas que podrían ayudar con esto

## Solución 
A traves de Gihdra nos pudimos apoyar con está herramienta, para poder realizar un código mucho más legible para nosotros como usuarios, además que realizamos el siguiente archivo de python para poder aplicar el inverso de nuestro archivo:

cifrado = open ('rev_this' , 'r').read()

print(cifrado)

flag = ''
for i in  range(8, len(cifrado)-1):
       if  i & 1 == 0: 
                flag += chr(ord(cifrado[i]) - 5)
       else:
               flag += chr(ord(cifrado[i]) + 2)

print(flag)

Con este pequeño archivo de python pudimos solucionar nuestro reto.

## Contraseña obtenida 
picoCTF{r3v3rs312528e05}
## Notas 
Es importante saber como poder utilizar todas nuestras herramientas que nos pueden ayudar a solucionar nuestros retos inversos. Además de también es importante un código legible, para poder aplicar lo necesario en nuestros archivos.
## Referencias
No necesite referencias.