## Descripción del reto
Ejecute el script runme.py para obtener la bandera. Descargue el script con su navegador o con wget en webshell.
Descargar el script Python runme.py
## Pistas 
1.- Si tiene Python en su computadora, puede descargar el script normalmente y ejecutarlo. De lo contrario, utilice el comando wget en el webshell.

2.-Para usar wget en el webshell, primero haga clic derecho en el enlace de descarga y seleccione "Copiar enlace" o "Copiar dirección de enlace".

3.-Escriba todo después del signo de dólar en el shell web: $ wget, luego pegue el enlace después del espacio después de wget y presione Entrar. ¡Esto descargará el script en el webshell para que puedas ejecutarlo!

4.- Finalmente, para ejecutar el script, escriba todo lo que aparece después del signo de dólar y luego presione Intro: $ python3 runme.py ¡Debería tener la bandera ahora!

## Solución 
`resm-picoctf@webshell:~$ mkdir runme` 
`resm-picoctf@webshell:~$ cd runme/`
`resm-picoctf@webshell:~/runme$ wget https://artifacts.picoctf.net/c/34/runme.py`
`--2024-03-02 19:56:47--  https://artifacts.picoctf.net/c/34/runme.py`
`Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.43, ...`
`Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 270 [application/octet-stream]`
`Saving to: 'runme.py'`

`runme.py                                        100%[======================================================================================================>]     270  --.-KB/s    in 0s`      

`2024-03-02 19:56:47 (12.1 MB/s) - 'runme.py' saved [270/270]`

`resm-picoctf@webshell:~/runme$ ls`
`runme.py`
`resm-picoctf@webshell:~/runme$ python runme.py` 
`picoCTF{run_s4n1ty_run}`


 
## Contraseña obtenida 
picoCTF{run_s4n1ty_run}
## Notas 
Aquí se puede apreciar que el comando pyhton sirve para poder ejectuar archivos con la extensión .py ya que este formato fue en el que se desacargo nuestro archivo. 
## Referencias 
No hay referencias, debido a que los comandos ya se tenian en cuenta en niveles anteriores.