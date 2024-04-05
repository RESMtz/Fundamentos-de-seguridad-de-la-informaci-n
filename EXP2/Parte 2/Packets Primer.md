## Descripción del reto
Descargue el archivo de captura de paquetes y utilice un software de análisis de paquetes para encontrar la bandera.
Descargar captura de paquetes
## Pistas 
Wireshark, si puede instalarlo y usarlo, es probablemente el producto de software de análisis de paquetes más amigable para principiantes.
## Solución 
Comenzamos descargando nuestra captura de datos:
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Packets Primer]
└─$ wget https://artifacts.picoctf.net/c/195/network-dump.flag.pcap          
--2024-04-04 17:58:30--  https://artifacts.picoctf.net/c/195/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap                    100%[====================================================================================>]     778  --.-KB/s    in 0s      

2024-04-04 17:58:31 (9.21 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Packets Primer]
└─$ ls
network-dump.flag.pcap
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Packets Primer]
└─$ open network-dump.flag.pcap 
Para previamente, le damos clic derecho al primer paquete despues de eso le damos clic en la opcion follow, para que finalmente nos muestre nuestra bandera: 
p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ b 9 d 5 3 7 6 5 }
Ya nada mas concatenamos nuestra bandera y finalmente obtenemos nuestra flag 
## Contraseña obtenida 
picoCTF{p4ck37_5h4rk_b9d53765}

## Notas
Es importante saber funciones básicas de nuestro wireshark ya que esta herramienta nos permite obtener datos adicionales. 
## Referencias 
No requerí fuentes externas.