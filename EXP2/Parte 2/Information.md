## Descripción del reto

Los archivos siempre se pueden cambiar de forma secreta. ¿Puedes encontrar la bandera? gato.jpg
## Pistas 
Mira los detalles del archivo.
Asegúrese de enviar la bandera como picoCTF{XXXXX}
## Solución 
└─$ wget https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg                
--2024-04-04 16:41:00--  https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                                   100%[====================================================================================>] 857.55K  1.73MB/s    in 0.5s    

2024-04-04 16:41:02 (1.73 MB/s) - ‘cat.jpg’ saved [878136/878136]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/information]
└─$ file cat.jpg                                  
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/information]
└─$ exiftool cat.jpg     
ExifTool Version Number         : 12.76
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2024:04:04 16:41:06-04:00
File Inode Change Date/Time     : 2024:04:04 16:41:02-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/information]
└─$ base64 --help
Usage: base64 [OPTION]... [FILE]
Base64 encode or decode FILE, or standard input, to standard output.

With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -d, --decode          decode data
  -i, --ignore-garbage  when decoding, ignore non-alphabet characters
  -w, --wrap=COLS       wrap encoded lines after COLS character (default 76).
                          Use 0 to disable line wrapping
      --help        display this help and exit
      --version     output version information and exit

The data are encoded as described for the base64 alphabet in RFC 4648.
When decoding, the input may contain newlines in addition to the bytes of
the formal base64 alphabet.  Use --ignore-garbage to attempt to recover
from any other non-alphabet bytes in the encoded stream.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/base64>
or available locally via: info '(coreutils) base64 invocation'

Finalmente pude observar bien en la licencia que tiene una linea de comando en base 64, la cual me apoye en un decodificador online para poder decifrarla. 
## Contraseña obtenida 
picoCTF{the_m3tadata_1s_modified}
## Referencias
https://www.base64decode.org/es/