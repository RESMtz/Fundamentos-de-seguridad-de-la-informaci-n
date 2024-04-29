## Descripción del reto
¿Puedes conseguir la bandera?
Descarga este [binario](https://artifacts.picoctf.net/c/86/gdbme).
Aquí están las instrucciones de prueba de manejo:
- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Pistas 
No hay pistas 

## Solución
resm-picoctf@webshell:~$  chmod +x gdbme
resm-picoctf@webshell:~$ gdb gdbme
GNU gdb (Ubuntu 12.1-0ubuntu1~22.04) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm

`
``(gdb) break *(main+99)`  
`(gdb) run`  
`Starting program: /home/resm-picoctf/gdbme`  
`warning: Error disabling address space randomization: Operation not permitted [Thread debugging using libthread_db enabled]`  
`Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".`  
`Breakpoint 1, 0x000055b73e5ca32a in main ()`  
`(gdb) jump *(main+104)`  
`Continuing at 0x55b73e5ca32f. picoCTF{d3bugg3r_dr1v3_72bd8355}`

## Contraseña obtenida
picoCTF{d3bugg3r_dr1v3_72bd8355}
## Notas 
El reto es muy sencillo en cuestión basta con usar la consola que nos brinda nuestra plataforma. Debido a que nos brinda nuestros respectivos comandos solo basta con aplicarlos y nos arroja automaticamente la bandera.
## Referencias 
No use referencias en este caso.