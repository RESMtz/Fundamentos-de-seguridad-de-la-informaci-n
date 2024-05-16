## Descripción del reto
¿Puedes averiguar qué hay en el registro eax al final de la función principal? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Depura [esto.](https://artifacts.picoctf.net/c/520/debugger0_b)
## Pistas 
Puede calcular eax usted mismo o puede establecer un punto de interrupción después del cálculo e inspeccionar eax para permitir que el programa haga el trabajo pesado por usted.
## Solución 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 2]
└─$ ls
debugger0_b
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 2]
└─$ chmod +x debugger0_b                                
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/GDB Baby Step 2]
└─$ gdb -q debugger0_b
Reading symbols from debugger0_b...
(No debugging symbols found in debugger0_b)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x40110e
(gdb) run
Starting program: /home/kali/Desktop/ExamenParcial3/GDB Baby Step 2/debugger0_b 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040110e in main ()
(gdb) break *0x401142
Breakpoint 2 at 0x401142
(gdb) c
Continuing.

Breakpoint 2, 0x0000000000401142 in main ()
(gdb) print/d $eax
$1 = 307019
(gdb) Quit

## Contraseña obtenida 
picoCTF{307019}
## Notas
Es importante saber realizar los breakpoints, ya que así se toma en cuenta como se va corriendo paso a paso. 

## Referencias 
[https://moisesrbb.tripod.com/unidad5.htm#u5110](https://moisesrbb.tripod.com/unidad5.htm#u5110) [https://sourceware.org/gdb/](https://sourceware.org/gdb/)
