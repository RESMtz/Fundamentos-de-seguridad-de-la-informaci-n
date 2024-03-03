## Descripción del reto
¿Puedes invocar indicadores de ayuda para una herramienta o binario? Este programa tiene información extraordinariamente útil...
## Pistas 
1.- Este programa solo funcionará en webshell u otra computadora con Linux.

2.- Para que se pueda acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal: $ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm

3.- Ejecute este programa ingresando lo siguiente en el indicador de Terminal: $ ./warm, pero primero deberá hacerlo ejecutable con $ chmod +x warm

4.- -h y --help son los argumentos más comunes que se dan a los programas para obtener más información de ellos.

5.- No todos los programas implementan funciones de ayuda como -h y --help.
## Solución 

Primero descargue el programa con mi comando wget, luego previamente comprobe que existe el archivo en el directorio con ls.

resm-picoctf@webshell:~$ ls            
README.txt  flag  flag.1  warm

Una vez comprobando esto, aplicamos chmod +x para permitir ejecutar el archivo, una vez aplicando el comando podemos ejecturalo con ./nombre_del_programa 
resm-picoctf@webshell:~$ chmod +x warm
resm-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!

Para finalmente darle uso a la pista que se nos brindo en el número 5 y así poder obtener nuestra bandera:
resm-picoctf@webshell:~$ ./warm -h 
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
resm-picoctf@webshell:~$ 
## Contraseña obtenida 
picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
## Notas 
Aquí pude implementar el chmod, que nos ayuda a dar distintos permisos sobre un archivo, por ejemplo aquí nos dejo ejecutar debido al +x que esto indica que nos de permiso de ejecutar dicho archivo.
## Referencias 
https://www.ibm.com/docs/es/aix/7.1?topic=groups-changing-file-directory-permissions#:~:text=Utilice%20el%20mandato%20chmod%20para%20cambiar%20los%20permisos%20de%20los%20archivos.&text=Esto%20a%C3%B1ade%20el%20permiso%20de,los%20archivos%20chap1%20y%20chap2.&text=Esto%20otorga%20permiso%20de%20lectura,archivo%20(u%3Drwx).
