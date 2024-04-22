## Descripción del reto
Tu misión es ingresar al laboratorio del Dr. Evil y recuperar los planos de su Proyecto Doomsday. El laboratorio está protegido por una serie de puertas de bóveda cerradas con llave. Cada puerta está controlada por una computadora y requiere una contraseña para abrirse. Desafortunadamente, nuestros agentes encubiertos no han podido obtener las contraseñas secretas de las puertas de la bóveda, ¡pero uno de nuestros agentes junior obtuvo el código fuente de la computadora de cada bóveda! Deberá leer el código fuente de cada nivel para descubrir cuál es la contraseña para la puerta de esa bóveda. Como calentamiento, hemos creado una réplica del salto en nuestras instalaciones de entrenamiento. El código fuente de la bóveda de entrenamiento está aquí: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)

## Pistas 
La contraseña se revela en el código fuente del programa.
## Solución 
Para comenzar bajamos nuestro archivo correspondiente: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-training]
└─$ wget https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java
--2024-04-22 03:28:05--  https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 943 [application/octet-stream]
Saving to: ‘VaultDoorTraining.java’

VaultDoorTraining.java                    100%[===================================================================================>]     943  --.-KB/s    in 0s      

2024-04-22 03:28:05 (11.2 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

--------------------------------------------------------------------
Ahora ya bajado descargue el compliador de Java. 

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-training]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
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

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_3808d338b46");
    }
}
Una vez que lo abrimos con Cat nos muestra el código de arriba.

Entonces para ello ejecutamos nuestro programa en java y vemos que nos arroja un password.
picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}
Al ejecutar esto con java nos arroja lo siguiente: 

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-training]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}   
Access granted.

Ahora vemos que nos da acceso garantizado, y deducimos que está es la flag en este nivel.

## Contraseña obtenida 
picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}
## Notas 
En este caso, es un ejemplo muy sencillo de ingeniera inversa. Espero poder seguir aprendiendo más a fondo estos métodos.
## Referencias
https://www.creaform3d.com/blog/es/que-es-ingenieria-inversa/
