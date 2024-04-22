## Descripción del reto
Esta bóveda utiliza bucles for y matrices de bytes. El código fuente de esta bóveda está aquí: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)
## Pistas 
Cree una tabla que contenga cada valor de las variables del bucle y el índice del búfer correspondiente en el que escribe.
## Solución 
Para empezar comenzamos descargando nuestro archivo, previamente en la carpeta lo abrimos con cat. Una vez abierto, vemos que nos arroja un código de java. Nos dirigimos al navegador FireFox y damos click derecho e inspeccionar, luego a la pestaña de consola y pegamos lo siguiente: 

var password = "jU5t_a_sna_3lpm12g94c_u_4_m7ra41";
undefined
var buffer = Array(32);
undefined
for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
Luego de esto ejecutamos el siguiente comando: 
buffer.join("")

"jU5t_a_s1mpl3_an4gr4m_4_u_c79a21"
Vemos que nos arroja la bandera, y le damos su formato adecuado 

## Contraseña obtenida 
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_c79a21}
## Notas 
Es importante saber analizar nuestros códigos en java, para saber como ejecutar y saber el orden de los caracteres, además que aprendí a ejecutar distintos métodos de ingeniera inversa
## Referencias 
No recurrí a fuentes externas.
