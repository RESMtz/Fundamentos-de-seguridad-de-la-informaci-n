## Descripción del reto
Encontramos esta captura de paquete. Recupera la bandera que fue sustraída de la red.
## Pistas 

## Solución 
──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic]
└─$ mkdir wireshark2
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic]
└─$ cd wireshark2 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/wireshark2]
└─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
--2024-03-16 04:36:06--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.13
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.1
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[==================================

2024-03-16 04:36:07 (768 KB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/wireshark2]
└─$ ls
capture.pcap

Mediante un archivo de python codificamos lo siguiente:
from scapy.all import *

flag = ''
packets = rdpcap('capture.pcap')
for p in packets:
           if UDP in p and p[UDP].dport == 22:
                   if p[UDP].sport > 5000:
                           flag +=chr(p[UDP].sport - 5000)
print(flag)

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/wireshark2]
└─$ python exp.py
Una vez ejecutado obtenemos el flag: 
picoCTF{p1LLf3r3d_data_v1a_st3g0}



## Contraseña obtenida 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
## Notas 
Aprendí a manipular más a detalle lo que viene siendo el wire shark, y lo importante que numeración tiene cada uno de ellos. Además que me ayudo a manipular a detalle lo que viene siendo los paquetes. 
## Referencias 
No utilice referencias.