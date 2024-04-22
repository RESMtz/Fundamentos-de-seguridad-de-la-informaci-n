## Descripción del reto
En el último desafío, dominaste los números octales (base 8), decimales (base 10) y hexadecimales (base 16), ¡pero esta puerta de bóveda utiliza un cambio de base y codificación de URL diferente! El código fuente de esta bóveda está aquí: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)
## Pistas 
Puede que le resulte útil una herramienta de codificación/descodificación, como https://encoding.tools/
Lea los artículos de Wikipedia sobre codificación de URL y codificación base 64 para comprender cómo funcionan y cómo se ven los resultados.

## Solución 
Comenzamos descargando el código, después lo abrimos con el comando cat: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/vault-door-5]
└─$ cat VaultDoor5.java 
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
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

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1";
        return base64Encoded.equals(expected);
    }
}
Hay una parte importante, la cual es la siguiente: 
String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1";
Por los simbolos podemos ver que es una concatenación además de que el formato del texto podemos decir que está cifrado. En base64 ahora mediante la herramienta cyber chief, le colocamos la cadena junta y nos traduce nuestra flag finalmente. 
## Contraseña obtenida
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}
## Notas 
Es importante saber como decodificar cierto tipo de información, a lo largo de estos niveles descubri mucho lo útil que puede ser la ingeniera inversa.
## Referencias 
https://gchq.github.io/CyberChef/#recipe=To_Base64('A-Za-z0-9%2B/%3D')From_Base64('A-Za-z0-9%2B/%3D',true,false)From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRNNEpUTTBKVFkySlRZMEpUTTFKVE13SlRNNUpUTTE&ieol=CRLF&oeol=CRLF