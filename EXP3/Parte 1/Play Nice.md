## Descripción del reto
No todos los cifrados antiguos eran tan malos... La bandera no tiene el formato estándar. nc mercury.picoctf.net 19354 [playfair.py](https://mercury.picoctf.net/static/9ea1604c8767cd6545948ad54670c2bf/playfair.py)

## Pistas
-
## Solución 
Primeramente bajamos y abrimos el archivo python al abrir nos arroja el siguiente código: 
#!/usr/bin/python3 -u
import signal

SQUARE_SIZE = 6


def generate_square(alphabet):
        assert len(alphabet) == pow(SQUARE_SIZE, 2)
        matrix = []
        for i, letter in enumerate(alphabet):
                if i % SQUARE_SIZE == 0:
                        row = []
                row.append(letter)
                if i % SQUARE_SIZE == (SQUARE_SIZE - 1):
                        matrix.append(row)
        return matrix

def get_index(letter, matrix):
        for row in range(SQUARE_SIZE):
                for col in range(SQUARE_SIZE):
                        if matrix[row][col] == letter:
                                return (row, col)
        print("letter not found in matrix.")
        exit()

def encrypt_pair(pair, matrix):
        p1 = get_index(pair[0], matrix)
        p2 = get_index(pair[1], matrix)

        if p1[0] == p2[0]:
                return matrix[p1[0]][(p1[1] + 1)  % SQUARE_SIZE] + matrix[p2[0]][(p2[1] + 1)  % SQUARE_SIZE]
        elif p1[1] == p2[1]:
                return matrix[(p1[0] + 1)  % SQUARE_SIZE][p1[1]] + matrix[(p2[0] + 1)  % SQUARE_SIZE][p2[1]]
        else:
                return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

def encrypt_string(s, matrix):
        result = ""
        if len(s) % 2 == 0:
                plain = s
        else:
                plain = s + "n5vgru7ehz1klja8s9340m2wcxbd6pqfitoy"[0]
        for i in range(0, len(plain), 2):
                result += encrypt_pair(plain[i:i + 2], matrix)
        return result

alphabet = open("key").read().rstrip()
m = generate_square(alphabet)
msg = open("msg").read().rstrip()
enc_msg = encrypt_string(msg, m)
print("Here is the alphabet: {}\nHere is the encrypted message: {}".format(alphabet, enc_msg))
signal.alarm(18)
resp = input("What is the plaintext message? ").rstrip()
if resp and resp == msg:
        print("Congratulations! Here's the flag: {}".format(open("flag").read()))

https://en.wikipedia.org/wiki/Playfair_cipher
Para ello podemos ver que el tamaño es 6 en las primeras lineas, esto es importante debido a que nos arroja el tamaño del alfabeto.

Ahora aplicamos el comando nc
Y nos arroja lo siguiente: 
──(kali㉿kali)-[~/Desktop/ExamenParcial3/Play nice]
└─$ nc mercury.picoctf.net 19354
Here is the alphabet: n5vgru7ehz1klja8s9340m2wcxbd6pqfitoy
Here is the encrypted message: hnjm2e4t51v16gsg104i4oi9wmrqli
What is the plaintext message?

Vemos que nos arroja mensaje y alfabeto, tenemos que redimensionar el tamaño del alfabeto en nuestra herramienta online, entonces para ello consideramos el tamaño cambiamos 6 por 6 y vemos que nos arroja un mensaje. 

En los campos abajo del alfabeto introducimos: 
n5vgru7ehz1klja8s9340m2wcxbd6pqfitoy
Y en el campo siguiente: 
 hnjm2e4t51v16gsg104i4oi9wmrqli
 Ahora podemos aplicar el comando siguiente: 
 python3 -c "print('7V8441MFRERHDR8RH20F2FYA20NOAQ'.lower())"
└─$ python3 -c "print('7V8441MFRERHDR8RH20F2FYA20NOAQ'.lower())"
7v8441mfrerhdr8rh20f2fya20noaq

Ahora lo que nos arrojo lo introducimos en el comando nc: 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Play nice]
└─$ nc mercury.picoctf.net 19354                                
Here is the alphabet: n5vgru7ehz1klja8s9340m2wcxbd6pqfitoy
Here is the encrypted message: hnjm2e4t51v16gsg104i4oi9wmrqli
What is the plaintext message? 7v8441mfrerhdr8rh20f2fya20noaq
Congratulations! Here's the flag: dbc8bf9bae7152d35d3c200c46a0fa30


## Contraseña obtenida 
dbc8bf9bae7152d35d3c200c46a0fa30
## Notas 
Es importante saber que no solo podemos aprovechar herramientas internas, si no que también ya hay muchas herramientas que nos auxilien a poder realizar tareas de manera mucho más sencilla para poder obtener información que está tratando de obtenerse 
## Referencias 
https://www.dcode.fr/playfair-cipher
