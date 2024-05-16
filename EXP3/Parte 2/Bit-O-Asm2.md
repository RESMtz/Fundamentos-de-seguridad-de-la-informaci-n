## Descripción del reto
¿Puedes averiguar qué hay en el registro eax? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Descargue el volcado de ensamblaje [aquí.](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt)

## Pistas 
Los PTR o 'punteros' hacen referencia a una ubicación en la memoria donde se pueden almacenar valores.

## Solución 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ cat disassembler-dump0_b.txt             
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii (0x9fe1a)
'654874'
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ cat disassembler-dump0_b.txt             
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm2]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii (0x9fe1a)
'654874'

## Contraseña obtenida 
picoCTF{654874}
## Notas 
Es muy similar a la parte 1, debido a que nos ayuda a poder obtener con un método bastante similar. 
## Referencias 
http://www.sc.ehu.es/sbweb/webcentro/automatica/web_8051/Contenido/cursoc51/Capitulo%206/uso_de_punteros_y_arrays_en_c51.htm#:~:text=El%20puntero%20es%20el%20equivalente,de%20otra%20variable%20o%20constante.
