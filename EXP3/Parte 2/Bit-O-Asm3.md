## Descripción del reto
¿Puedes averiguar qué hay en el registro eax? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Descargue el volcado de ensamblaje [aquí](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Pistas 
No todo lo que aparece en este listado de desmontaje es óptimo.
## Solución 
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm3]
└─$ ls
disassembler-dump0_c.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm3]
└─$ cat disassembler-dump0_c.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm3]
└─$ python3                                                          
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> eax=0x9fe1a
>>> hex(0x9fe1a*0x4)
'0x27f868'
>>> hex(0x27f868+0x1f5)
'0x27fa5d'
>>> ascii(0x27fa5d)
'2619997'

## Contraseña obtenida 
picoCTF{2619997}
## Notas 
Es importante saber operar en python ya que de está forma podemos obtener nuestra bandera de manera correcta.
## Referencias 
https://www.studocu.com/co/document/servicio-nacional-de-aprendizaje/programacion/clase-05-programacion-python-ensambladores-compiladores-interpretes/15485949