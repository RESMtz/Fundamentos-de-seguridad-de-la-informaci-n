## Descripción del reto
Encuentra la bandera en esta imagen.
URL de la imagen: https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png

## Pistas
¿Qué significa meta en el contexto de los archivos?

¿Has oído hablar alguna vez de los metadatos?
## Solución 
1.- Primeramente colocamos la imagen en nuestro directorio y entramos a el: 
┌──(kali㉿kali)-[~]
└─$ cd Desktop/
┌──(kali㉿kali)-[~/Desktop]
└─$ ls         
'Retos picoCTF'
 
┌──(kali㉿kali)-[~/Desktop]
└─$ cd Retos\ picoCTF 

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ ls               
'Retos forensic'

┌──(kali㉿kali)-[~/Desktop/Retos picoCTF]
└─$ cd Retos\ forensic 
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic]
└─$ ls
'glory of the garden'  'So Meta'
  ┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic]
└─$ cd So\ Meta       
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/So Meta]
└─$ ls
pico_img.png
2.- Una vez ubicado aplicamos el comando 
exiftool, este comando se utiliza para ver los metadatos de un archivo.
┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Retos forensic/So Meta]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 12.76
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2024:03:12 19:46:20-04:00
File Access Date/Time           : 2024:03:12 19:46:43-04:00
File Inode Change Date/Time     : 2024:03:12 19:46:43-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
Una vez aplicado este comando se pueden ver los metadatos de nuestro archivo. Dicho archivo en el apartado de artista vemos que contiene nuestro flag. 
## Contraseña obtenida 
 picoCTF{s0_m3ta_d8944929}
## Notas 
Aprendí a el nuevo uso del comando exiftool, el cual como se menciona. Nos permite reconocer los metadatos de nuestros archivos.
## Referencias 
https://esgeeks.com/exiftool-extraer-metadatos-archivos/
https://www.geoidep.gob.pe/catalogo-metadatos/que-son-los-metadatos
