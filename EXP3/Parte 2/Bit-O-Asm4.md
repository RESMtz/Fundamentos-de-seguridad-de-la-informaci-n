## Descripción del reto
¿Puedes averiguar qué hay en el registro eax? Coloque su respuesta en el formato de indicador picoCTF: picoCTF{n} donde n es el contenido del registro eax en la base numérica decimal. Si la respuesta fuera 0x11, tu indicador sería picoCTF{17}.
Descargue el volcado de ensamblaje [aquí.](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt)

## Pistas 
No le digas a nadie que te dije esto, pero puedes resolver este problema sin comprender la relación de comparación/salto.

Por supuesto, si eres realmente bueno, sólo necesitarás un intento para resolver este problema.

## Solución 
`┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm4]`
`└─$ ls`
`disassembler-dump0_d.txt`
                                                                                                                                                                       
`┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm4]`
`└─$ cat disassembler-dump0_d.txt`
`<+0>:     endbr64` 
`<+4>:     push   rbp`
`<+5>:     mov    rbp,rsp`
`<+8>:     mov    DWORD PTR [rbp-0x14],edi`
`<+11>:    mov    QWORD PTR [rbp-0x20],rsi`
`<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a`
`<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710`
`<+29>:    jle    0x55555555514e <main+37>`
`<+31>:    sub    DWORD PTR [rbp-0x4],0x65`
`<+35>:    jmp    0x555555555152 <main+41>`
`<+37>:    add    DWORD PTR [rbp-0x4],0x65`
`<+41>:    mov    eax,DWORD PTR [rbp-0x4]`
`<+44>:    pop    rbp`
`<+45>:    ret`
                                                                                                                                                                       
`┌──(kali㉿kali)-[~/Desktop/ExamenParcial3/Bit-o-asm4]`
`└─$ python3`
`Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux`
`Type "help", "copyright", "credits" or "license" for more information.`
>>> `hex(0x2710>=0x9fe1a)`
`'0x0'`
>>> `hex(0x9fe1a-0x65)`
`'0x9fdb5'`
>>>  `ascii(0x9fdb5)`
  `File "<stdin>", line 1`
    `ascii(0x9fdb5)`
`IndentationError: unexpected indent`
`>>> ascii(0x9fdb5)`
`'654773'`


## Contraseña obtenida 
picoCTF{654773}
## Notas 
Es importante tomar en cuenta las pistas ya que de está manera pude obtener la contraseña adecuada.
## Referencias 
https://es.linkedin.com/advice/0/how-do-you-perform-conditional-jump-assembly-language?lang=es