## Descripción del reto
Descifremos esto:  [ciphertext](https://jupiter.challenges.picoctf.org/static/eb5e6df8e14c52873cf88c582a1a4008/ciphertext)? Algo parece un poco pequeño.
## Pistas 
RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
¿Cómo podría tener una e demasiado pequeña afectar la seguridad de esta clave de 2048 bits?
Asegúrate de no perder precisión, los números son bastante grandes (aparte del valor e)

## Solución 
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import  *
>>> from Crypto.Util.number import long_to_bytes
>>> 
>>> gmpy2.get_context().precision=2048
>>> 
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650080519263755075355825243327515211479747536697517688468095325517209911688684309894900992899707504087647575997847717180766377832435022794675332132906451858990782325436498952049751141 
>>> 
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203722801043052339225981)
>>> print( long_to_bytes (root))
b'picoCTF{n33d_a_lArg3r_e_d0cd6eae}'

## Contraseña obtenida 
picoCTF{n33d_a_lArg3r_e_d0cd6eae}
## Notas 
Es importante saber obtener las cosas con precision, ya que está es la que con exactitud nos arroja los datos.
## Referencias 
https://es.wikipedia.org/wiki/RSA
https://www.veritas.com/es/mx/information-center/rsa-encryption

