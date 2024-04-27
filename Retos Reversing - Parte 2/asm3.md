## Descripción del reto
¿asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) regresa? Envíe la bandera como un valor hexadecimal (comenzando con '0x'). NOTA: Su envío para esta pregunta NO estará en el formato de bandera normal. [Fuente](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

## Pistas 

## Solución 
Bajamos el archivo correspondiente en el directorio, ponemos en el siguiente comando: 
start: 
    push 0xbb86a173 
	push 0xd101e3dd
	push 0xba6c5a02
	call asm3 
asm3:
           push   ebp
           mov    ebp,esp
           xor    eax,eax
           mov    ah,BYTE PTR [ebp+0xb]
           shl    ax,0x10
          sub    al,BYTE PTR [ebp+0xd]
          add    ah,BYTE PTR [ebp+0xc]
          xor    ax,WORD PTR [ebp+0x12]
          nop
          pop    ebp
          ret   
Considerando los 3 valores que se me asignaron a mí lo fui corriendo paso por paso. Lo cual al final de correr esto nos arroja el valor de EAX, lo cual es nuestra contraseña que obtenemos.

## Contraseña obtenida 
0x669B
## Notas
Es importante saber las instrucciones y herramientas a tomar en cuenta. Para poder saber que podemos hacer, por ejemplo en este caso fue importante saber meterle los push. Ya que el push, nos ayuda a introduccir las variables. 
## Referencias 
https://carlosrafaelgn.com.br/Asm86/
