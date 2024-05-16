## Descripción del reto
Hace poco me enteré del criptosistema de clave pública SRA... o espera, ¿se suponía que era RSA? Hmmm, probablemente debería comprobarlo...
Detalles adicionales estarán disponibles después de lanzar su instancia de desafío.
## Pistas 
Conéctese al programa en nuestro servidor: nc saturn.picoctf.net 62468
Descarga el programa: [chal.py](https://artifacts.picoctf.net/c/295/chal.py)

## Solución 

Usaremos el siguiente código: 
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

def sub_lists (l):
    comb = []

    for i in range(1,len(l)+1):
        comb += [list(j) for j in combinations(l, i)]
    return comb

def divisors(phi):
   print("Dame los divisores de ", phi-1)
   return(eval(input()))


r = remote('saturn.picoctf.net', 52069)

r.recvuntil("anger =")
ciphertext=int(r.recvline())

r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()

factors=divisors(d*65537)
combos = sub_lists(factors)
En un archivo tipo python podemos obtener una cadena de números que permiten obtener mediante una herramienta online, la cual nos permite factorizar, por espacios y comas. 

Ejecutando esto nos arroja la cadena de números. 
Finalmente lo metemos a nuestra [herramienta](https://www.dcode.fr/prime-factors-decomposition) que factoriza
Ejecuantado el archivo con la cadena de numeros factorizada podemos obtener lo siguiente: 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/SRA]
└─$ python sra2.py
[+] Opening connection to saturn.picoctf.net on port 52069: Done
/home/kali/Desktop/ExamenParcial3/SRA/sra2.py:20: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/Desktop/ExamenParcial3/SRA/sra2.py:23: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 59253285257412479071535875443163628840892034575857625283742569702567967805837
d= 31886332953769031124805566137274728863612432458422057805157255809809953295673
/home/kali/Desktop/ExamenParcial3/SRA/sra2.py:27: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Dame los divisores de  2089734602791160992826382387938573905534567986027606402376591074007514909138521400
2, 2, 2, 5, 5, 359, 3011, 241313, 8134363, 76358305698086985917993629, 64490446382132990351146424279591693
{299771642114126099609927496711786916703, 231520702511857435360615663163734177871}
t42RixmE6TaiFOgv
/home/kali/Desktop/ExamenParcial3/SRA/sra2.py:53: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> t42RixmE6TaiFOgv\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}\r\n'
t42RixmE6TaiFOgv
[*] Closed connection to saturn.picoctf.net port 52069

## Contraseña obtenida 
picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}
## Notas 
Aprendí el concepto de descomposición el cual nos permite obtener datos bastante interesantes. El cual nos puede apoyar para poder obtener las contraseñas adecuadas.
## Referencias 
https://www.dcode.fr/prime-factors-decomposition
[https://es.wikipedia.org/wiki/RSA](https://es.wikipedia.org/wiki/RSA) 
