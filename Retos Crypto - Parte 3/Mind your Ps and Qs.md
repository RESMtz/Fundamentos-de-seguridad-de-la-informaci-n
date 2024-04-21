## Descripción del reto
En RSA, un valor e pequeño puede ser problemático, pero ¿qué pasa con N? ¿Puedes descifrar esto? valores
## Pistas 
Los bits son caros, usé solo un poco más de 100 para ahorrar dinero.
## Solución 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ mkdir "Mind your Ps and Qs"         
                                                                                 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ cd Mind\ your\ Ps\ and\ Qs 
                                                                                 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Mind your Ps and Qs]
└─$ wget https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values               
--2024-04-20 17:48:10--  https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values               100%[===================>]     206  --.-KB/s    in 0s      

2024-04-20 17:48:11 (159 MB/s) - ‘values’ saved [206/206]

                                                                                 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Mind your Ps and Qs]
└─$ ls
values
                                                                                 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Mind your Ps and Qs]
└─$ cat values                
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537   

---------------------------------------------------
Código en python3 que utilice para resolver 
>>> `c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667`
>>> `e = 65537`
>>> `p = 2159947535959146091116171018558446546179`
>>> `q = 658558036833541874645521278345168572231473`
>>> `n = p * q`
>>> `n`
`1422450808944701344261903748621562998784243662042303391362692043823716783771691667`
>>> `tn = (p-1)*(q-1)`
>>> `d = inverse (e,tn)`
`Traceback (most recent call last):`
  `File "<stdin>", line 1, in <module>`
`NameError: name 'inverse' is not defined. Did you mean: 'reversed'?`
`>>> from Crypyo.Util.number  import long_to_bytes`
`Traceback (most recent call last):`
  `File "<stdin>", line 1, in <module>`
`ModuleNotFoundError: No module named 'Crypyo'`
`>>> from Crypyo.Util.number  inverse`
  `File "<stdin>", line 1`
    `from Crypyo.Util.number  inverse`
                             `^^^^^^^`
`SyntaxError: invalid syntax`
`>>> from Crypto.Util.number  import long_to_bytes`
`>>> from Crypto.Util.number  inverse`
  `File "<stdin>", line 1`
    `from Crypto.Util.number  inverse`
                             `^^^^^^^`
`SyntaxError: invalid syntax`
`>>> from Crypto.Util.number inverse`
  `File "<stdin>", line 1`
    `from Crypto.Util.number inverse`
                            `^^^^^^^`
`SyntaxError: invalid syntax`
`>>> from Crypto.Util.number import inverse`
`>>> d = inverse (e,tn)`
`>>> m = pow(c, d, n)`
`>>> m`
`13016382529449106065927291425342535437996222135352905256639555294957886055592061`
`>>> long_to_bytes(m)`
`b'picoCTF{sma11_N_n0_g0od_00264570}'`

## Contraseña obtenida 
picoCTF{sma11_N_n0_g0od_00264570}
## Notas 
Es importante que en la mayoría de retos usemos el formato indicado en retos anteriores, debido a que es fundamental tomar en cuenta las herrmamientas anterirores.
## Referencias 
http://factordb.com/index.php?query=1422450808944701344261903748621562998784243662042303391362692043823716783771691667

