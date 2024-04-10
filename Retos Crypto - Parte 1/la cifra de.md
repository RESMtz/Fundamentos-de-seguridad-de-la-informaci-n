## Descripción del reto
Encontré este cifrado en un libro antiguo. ¿Puedes entender lo que dice? Conéctese con nc jupiter.challenges.picoctf.org 5726.
## Pistas 
Existen herramientas que lo hacen fácil.
Quizás mirar la historia ayude
## Solución 
Al hacer la conexión remota con nc podemos ver un texto cifrado, podemos ver que es un cifrado de vigenere pero nos topamos con que no tenemos la key para poder decifrar nuestro mensaje, entonces buscamos en el navegador web que nos apoye en este caso  Vigenère Solver
Al introducir el texto podemos ver que idioma y cuantos caracteres podemos selecionar, al ingresar estos datos podemos apoyarnos y finalmente obtener el texto decifrado con la flag. 

Zccltetyy bemnpgy:
It is interesting how in history people often receive credit for things they did not create

During the course of history, the Vigenère Cipher has been reinvented many times

It was falsely attributed to Blaise de Vigenère as it was originally described in 1553 by Giovan Battista Bellaso in his book La cifra del. Sig. Giovan Battista Bellaso 

For the implementation of this cipher a table is formed by sliding the lower half of an ordinary alphabet for an apparently random number of places with respect to the upper halfpicoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}

The first well-documented description of a polyalphabetic cipher however, was made around 1467 by Leon Battista Alberti.

The Vigenère Cipher is therefore sometimes called the Alberti Disc or Alberti Cipher.

In 1508, Johannes Trithemius invented the so-called tabula recta (a matrix of shifted alphabets) that would later be a critical component of the Vigenère Cipher.

Bellaso’s second booklet appeared in 1555 as a continuation of the first. The lower halves of the alphabets are now shifted regularly, but the alphabets and the index letters are mixed by means of a mnemonic key phrase, which can be different with each correspondent.

Finalmente podemos obtener nuestra flag.
## Contraseña obtenida 
picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}
## Notas 
Es importante saber que aunque podamos hacer cifrado de Vigenere que no necesariamente tenemos que acudir a nuestra key, que por medio de un texto también podemos obtener nuestros datos requeridos. 
## Referencias 
https://www.guballa.de/vigenere-solver

