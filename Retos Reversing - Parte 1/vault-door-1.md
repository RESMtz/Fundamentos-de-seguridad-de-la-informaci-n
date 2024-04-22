## Descripción del reto
¡Esta bóveda utiliza algunas matrices complicadas! Espero que pueda entenderlo, agente especial. El código fuente de esta bóveda está aquí:[ VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)

## Pistas
Busque el método charAt() en línea.
## Solución 
Comenzamos descargando el archivo:
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-1]
└─$ wget https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java       
--2024-04-22 03:43:39--  https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2264 (2.2K) [application/octet-stream]
Saving to: ‘VaultDoor1.java’

VaultDoor1.java                           100%[===================================================================================>]   2.21K  --.-KB/s    in 0s      

2024-04-22 03:43:39 (17.9 MB/s) - ‘VaultDoor1.java’ saved [2264/2264]

--------------------------------------------------------------------------

Ahora ejecutamos nuestro código: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-1]
└─$ cat VaultDoor1.java       
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
    }
}

--------------------------------------------------------------
Ahora metemos los caracteres en un archivo nano: 
password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4'

-------------------------------------------------------------
Ahora con esto ejecutamos, el siguiente comando: ─$ cat flg | sort 
Este nos permite acomodar en orden los caracteres. Pero nos arroja el texto con " ' ' " entonces para eliminarlas ejecutamos lo siguiente. 
cat flg | sort | awk '{print($3)}' | tr -d "'"

Nos arroja el texto sin comillas simples y ahora podemos copiar este texto para darle formato a nuestra bandera. Pero no sin antes eliminar el salto de linea para poder arrojar el texto todo junto. 

└─$ cat flg | sort | awk '{print($3)}' | tr -d "'"
d
3
5
c
r
4
m
b
l
3
_
t
H
3
_
c
H
4
r
4
c
T
3
r
5
_
f
6
d
a
f
4;
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-1]
└─$ cat flg | sort | awk '{print($3)}' | tr -d "'" | tr "/n"
tr: missing operand after ‘/n’
Two strings must be given when translating.
Try 'tr --help' for more information.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-1]
└─$ cat flg | sort | awk '{print($3)}' | tr -d "'" | tr -d "/n"
d
3
5
c
r
4
m
b
l
3
_
t
H
3
_
c
H
4
r
4
c
T
3
r
5
_
f
6
d
a
f
4
Finalmente le damos formato correcto a nuesta bandera.

## Contraseña obtenida 
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
## Notas 
En este nivel fue sencillo identificar el método, ya que en la misma pista nos arroja la ayuda. 
## Referencias 
https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/charAt
