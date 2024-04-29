## Descripción del reto
¿Qué puedes hacer con este archivo?
Olvidé la llave de mi caja fuerte, pero se supone que este [archivo](https://artifacts.picoctf.net/c/292/SafeOpener.class) me ayudará a recuperar la llave perdida. ¿Puedes ayudarme a desbloquear mi caja fuerte?
## Pistas 
Descargue e intente descompilar el archivo.
## Solución 
Descargamos nuestro archivo y podemos ver que si le aplicamos un cat se abre un tanto extraño el código: 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Safe Opener 2]
└─$ cat SafeOpener.class 
����4�
CDE     FG
H
I
JL      FN
OP
Q
RS
.T
OU
VW
X
Y
[
]
R`ab<init>()VCodeLineNumberTableLocalVariableTablethis
                                                      LSafeOpener;main([Ljava/lang/String;)VisOpenZargs[Ljava/lang/Stringkeyboard▒Ljava/io/BufferedReader;encodercEncoder
   InnerClasses▒Ljava/util/Base64$Encoder;
StackMapTable*Dcdang/String;keyiI
ExceptionsopenSafe(Ljava/lang/String;)password
SourceFileSafeOpener.java
                         java/io/BufferedReaderjava/io/InputStreamReaderf
                                                                         gh
                                                                           i
                                                                            jk
                                                                              lm
                                                                                noEnter password for the safe: p
                                                                                                                qr
                                                                                                                  std
                                                                                                                     uv
                                                                                                                       wx
                                                                                                                         yr
                                                                                                                           >?java/lang/StringBuilder
You have  
          z{
            z| attempt(s) left
                              }t,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}
                                                                             ~
                                                                              Sesame openPassword is incorrect

SafeOpenerjava/lang/Object▒java/util/Base64$Encoderjava/lang/Stringjava/io/IOExceptionjava/lang/SysteminLjava/io/InputStream;▒(Ljava/io/InputStream;)V(Ljava/io/Reader;)Vjava/util/Base64
getEncoder()Ljava/util/Base64$Encoder;outLjava/io/PrintStream;java/io/PrintStreamprint(Ljava/lang/String;)readLine()Ljava/lang/StringgetBytes()[BencodeToString([B)Ljava/lang/String;printlnappend-(Ljava/lang/String;)Ljava/lang/StringBuilder;(I)Ljava/lang/StringBuildertoStringequals(Ljava/lang/Object;)Z! /*��!"
                                                                                                                                                #$      %& <x�Y�Y���L�:6�T�
�
 +�
�.4>EKPq▒���HK,'�!▒!f+,b-1_23[43 X567� 89:;;�V<=        >? u▒L*+��
                    "#&'"@323�;AB0
.J/       

A grandes razgos nos muestra la flag, pero no es el objetivo del nivel, si no que nos dice que descompilar el archivo para esto indague en la red descubrí un decompilador de java el cual se llama jd-gui, despues de instalar este programa desde consola. Lo abrimos y seleccionamos nuestro archivo el cual el programa automaticamente nos arroja el siguiente código: 

public class SafeOpener {
  public static void main(String[] args) throws IOException {
    BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
    Base64.Encoder encoder = Base64.getEncoder();
    String encodedkey = "";
    String key = "";
    int i = 0;
    while (i < 3) {
      System.out.print("Enter password for the safe: ");
      key = keyboard.readLine();
      encodedkey = encoder.encodeToString(key.getBytes());
      System.out.println(encodedkey);
      boolean isOpen = openSafe(encodedkey);
      if (!isOpen) {
        System.out.println("You have  " + (2 - i) + " attempt(s) left");
        i++;
      } 
    } 
  }
  
  public static boolean openSafe(String password) {
    String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}";
    if (password.equals(encodedkey)) {
      System.out.println("Sesame open");
      return true;
    } 
    System.out.println("Password is incorrect\n");
    return false;
  }
}
Podemos obsevar que el mismo archivo ya decompilado nos muestra nuestra bandera mucho mejor.
## Contraseña obtenida 
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}
## Notas 
Es importante saber decompilar las cosas, fue bastante sencillo hacer esto. Debido a que basta con saber instalar nuestro decompilador y poder usarlo correctamente para realizar esto. 
## Referencias 
https://java-decompiler.github.io/