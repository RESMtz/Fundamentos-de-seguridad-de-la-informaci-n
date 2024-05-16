## Descripción del reto
¿Puedes averiguar qué hay en el registro eax? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Descargue el volcado de ensamblaje [aquí](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas 
Como ocurre con la mayoría de los ensamblajes, hay mucho ruido en el volcado de instrucciones. Encuentre la única línea que pertenece a esta pregunta y ¡no lo dude!

## Solución 
──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-05-15 22:15:40--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.62, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt                  100%[====================================================================================>]     209  --.-KB/s    in 0s      

2024-05-15 22:15:41 (185 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm1]
└─$ ls
disassembler-dump0_a.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm1]
└─$ cat disassembler-dump0_a.txt | grep "eax"
<+15>:    mov    eax,0x30
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm1]
└─$ python3       
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30",16))
48

## Contraseña obtenida 
picoCTF{48}
## Notas 
Es importante saber manipular el lenguaje python para poder realizar las tareas necesarias, en este caso fue indispensable hacerlo ya que de está manera se puede obtener nuestra password. 
## Referencias 
No requerí fuentes externas en este caso