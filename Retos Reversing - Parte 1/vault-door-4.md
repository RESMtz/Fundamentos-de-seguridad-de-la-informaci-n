## Descripción del reto
Esta bóveda utiliza codificación ASCII para la contraseña. El código fuente de esta bóveda está aquí: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)

## Pistas
Utilice un motor de búsqueda para encontrar una "tabla ASCII".
También necesitarás saber la diferencia entre números octales, decimales y hexadecimales.

## Solución 
Descargamos el archivo en directorio, para luego abrir el código: 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
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

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,
            'a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
    `
Ahora bien nos dirigimos al navegador FireFox, para previamente hacer click derecho e inspeccionar, luego a la pestaña de consola. Para pegar lo siguiente: 
String.fromCharCode (106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 , 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 )  

"jU5t_4_bUnCh_0f_bYt3s_f4"  

String.fromCharCode (106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,

            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ) + ['a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e'].join ('')

"jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e"

Vemos que elaborando los arreglos y dandole su respectivo join, podemos ver que nos arroja la password correcta. 
## Contraseña obtenida 
picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}
## Notas 
Es importante saber utilizar el formato de los códigos en java, aprender a manejar correctamente las listas, eso es lo que aprendí que también es importante el orden de estos.
## Referencias 
No recurrí a fuentes externas. 
