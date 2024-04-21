## Descripción del reto
Encontramos este extraño mensaje transmitiéndose a los servidores, creemos que tenemos un esquema de descifrado que funciona.
Descarga el mensaje aquí.
Tome cada número mod 37 y asígnelo al siguiente conjunto de caracteres: 0-25 es el alfabeto (mayúscula), 26-35 son los dígitos decimales y 36 es un guión bajo.
Envuelva su mensaje descifrado en el formato de bandera picoCTF (es decir, picoCTF{decrypted_message})
## Pistas
¿Sabes qué significa mod 37?
mod 37 significa módulo 37. Da el resto de un número después de dividirlo por 37.
## Solución
--------------------------------------------------
Código en python que se utilizo en este reto
datos = open('message.txt').read().split()

print(datos)

flag = ' '

for n in datos:
         c = int ( n ) % 37  
         if c >= 0  and c<= 25:
                        s = chr(c+65)
         elif c>=26 and c<=36:
                        s = chr (c+22) 
         else:
                       s = '_'
         flag +=       s
print(flag)

---------------------------------------------------------
Terminal de consola 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/basic-mod1]
└─$ python3 exp.py
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
 R0UND_N_R0UND_ADD17EC2


## Contraseña obtenida 
picoCTF{R0UND_N_R0UND_ADD17EC2}
## Notas 
Es importante saber elaborar splits, además de saber de que manejo de caracteres se está tratando.
## Referencias 
No necesite referencias 
