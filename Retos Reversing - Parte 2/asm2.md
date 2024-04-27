## Descripción del reto
¿Qué devuelve asm2(0xb,0x2e)? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)
## Pistas 
Condiciones de  [ensamblador](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)

## Solución 
                                                                      
stack 

[       ]< esp
[       ]< ebp - 0xc 
[ -0xffffff8b  ]< ebp - 0x8 
[  0x2f ]< ebp - 0x4 
[  ebp  ]< ebp
[  ret  ]< ebp + 0x4 
[  0xb  ]< ebp + 0x8 
[  0x2e ]< ebp + 0xc 

registers
[   ] eax

asm2: (0xb,0x2e)
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp

        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]

        <+40>:  leave
        <+41>:  ret

 




python3: 
┌──(kali㉿kali)-[~/Desktop/Reversing - Parte 2/asm2]
└─$ python3 
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xb<= 0x63f3
True
>>> hex(0x2e+0x1)
'0x2f'
>>> hex(0xb+0xffffff80)
'0xffffff8b'
>>> 0xffffff8b <= 0x63f3
False
>>> 0x2e + 0x1 
47
>>> hex (0x2e + 0x1)
'0x2f'
>>> hex (0xb + 0x1)
'0xc'
>>> hex (0xb + 0xffffff80)
'0xffffff8b'
>>> 0x63f3/0xffffff8b
5.95743784145923e-06
>>> hex (0xb - 0xffffff80)
'-0xffffff75'
>>> -0xffffff75 <=0x63f3
True
>>> 0x63f3 / -0xffffff8b
-5.95743784145923e-06
>>> int (0x2e)
46
>>> hex (46-5)
'0x29'
>>> 0x63f3 / 0xffffff8b
5.95743784145923e-06

## Contraseña obtenida 
0xf6
## Notas 
Es importante saber referenciar nuestras direcciones sin embargo, también es importante tener en cuenta que tipo de operaciones podemos obtener en nuestro programa. Por ejemplo en la línea 24 podemos ver un incremento o decremento, esto lo señalo porque en el vídeo al profesor le salío un add y a mí me salió un sub lo cual indica que no era hacer incremento, sino un decremento.
## Referencias 
https://www.cs.virginia.edu/~evans/cs216/guides/x86.html