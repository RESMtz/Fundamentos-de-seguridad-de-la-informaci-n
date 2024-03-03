## Descripción del reto
Ejecute el script Python y convierta el número dado de decimal a binario para obtener la bandera.
Descargar el script Python
## Pistas
1.- ¡Busque una aplicación de conversión de números decimales a binarios en la web o use la calculadora de su computadora!

2.- No es necesario realizar ingeniería inversa a la función str_xor para este desafío.

3.- Si tiene Python en su computadora, puede descargar el script normalmente y ejecutarlo. De lo contrario, utilice el comando wget en el webshell.

4.- Para usar wget en el webshell, primero haga clic derecho en el enlace de descarga y seleccione "Copiar enlace" o "Copiar dirección de enlace".

5.- Escriba todo después del signo de dólar en el shell web: $ wget, luego pegue el enlace después del espacio después de wget y presione Entrar. ¡Esto descargará el script en el webshell para que puedas ejecutarlo!

6.- Finalmente, para ejecutar el script, escriba todo lo que esté después del signo de dólar y luego presione enter: $ python3 convertme.py
## Solución
Primero descargamos y corroboramos que este el archivo dentro del directorio:
resm-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2024-03-02 17:58:39--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                    100%[======================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-03-02 17:58:39 (64.6 MB/s) - 'convertme.py' saved [1189/1189]

resm-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  code.py  codebook.txt  convertme.py
flag  flag.1  index.html  index.html.1  ltdis.sh  static  warm

Una vez ahí ejectuamos el archivo .py para poder ver que es lo que nos pide 
Como se ve nos pregunta cuanto es el 17 en binario, y respondemos nos arroja nuestro flag:
resm-picoctf@webshell:~$ python convertme.py
If 17 is in decimal base, what is it in binary base?
Answer: 10001
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
## Contraseña obtenida
picoCTF{4ll_y0ur_b4535_762f748e}
## Notas 
Es importante saber convertir y saber ejecutar archivos a la vez ya que es de gran utilidad y me ayudo de cierta manera a poder descifrar información con más eficacia.
## Referencias 
https://platzi.com/tutoriales/1474-oop/9286-como-ejecutar-programas-py-en-ubuntu/



