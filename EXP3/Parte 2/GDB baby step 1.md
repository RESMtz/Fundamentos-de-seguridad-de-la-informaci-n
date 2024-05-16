## Descripción del reto
¿Puedes averiguar qué hay en el registro eax al final de la función principal? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Desmonta [esto.](https://artifacts.picoctf.net/c/512/debugger0_a)

## Pistas 
¡gdb es un muy buen depurador para usar en este problema y muchos otros!
main es en realidad un símbolo reconocido que se puede usar con los comandos gdb.
## Solución 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 1]
└─$ ls
debugger0_a
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 1]
└─$ chmod +x debugger0_a
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 1]
└─$  gdb -q debugger0_a 
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
(gdb) quit
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 1]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x86342)
'549698'

## Contraseña obtenida 
picoCTF{549698}
## Notas 
Podemos obtener nuestra contraseña, la importancia de las pistas es a tomar en cuenta. Ya que con anterioridad podemos usar GDB para poder obtener nuestra pass. 
## Referencias 
[https://sourceware.org/gdb/](https://sourceware.org/gdb/)