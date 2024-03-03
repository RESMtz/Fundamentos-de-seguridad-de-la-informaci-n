## Descripción del reto
El uso de tabcomplete en la Terminal agregará años a su vida, especialmente. cuando se trata de estructuras de directorios y nombres de archivos largos y confusos: Addadshashanammu.zip
## Pistas 
Después de "descomprimir", este problema se puede resolver presionando 11 botones... (principalmente Tab)...
## Solución 
Primero comenzamos descargando nuestro archivo como es costumbre y aplicamos ls para comprobar que esta dentro del directorio: 

resm-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip
--2024-03-02 07:27:32--  https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4521 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                            100%[======================================================================================================>]   4.42K  --.-KB/s    in 0s      

2024-03-02 07:27:32 (2.08 GB/s) - 'Addadshashanammu.zip' saved [4521/4521]

resm-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  flag  flag.1  index.html  index.html.1  ltdis.sh  static  warm

Mediante el comando unzip descomprimimos el archivo con extensión ZIP, pero esta vez presionamos tabulador para completar el nombre y después nos dirigimos o cambiamos de directorio mediante tabulador : 
resm-picoctf@webshell:~$ unzip Addadshashanammu.zip                                           
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
resm-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/

Una vez dentro de todos los directorios comprobamos que archivos hay dentro
resm-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet

Una vez viendo que archivos hay, lo ejectuamos para ver que podemos obtener de esto
picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
resm-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 

Contraseña obtenida:
picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
## Contraseña obtenida
picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
## Notas 
Aquí en este nivel nos resaltan que importancia tiene el tabulador que nos ayuda a completar nombre ya sea de archivos o directorios, algo simple pero bastante útil.
## Referencias 
Aquí no coloque referencias, debido a que los comandos previos ya fueron utilizados.
