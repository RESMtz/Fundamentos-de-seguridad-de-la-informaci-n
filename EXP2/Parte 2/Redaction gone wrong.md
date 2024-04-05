## Descripción del reto
Ahora NO me ves.
Este informe contiene algunos datos críticos, algunos de los cuales han sido redactados correctamente, mientras que otros no. ¿Puedes encontrar una clave importante que no haya sido redactada correctamente?
## Pistas 
¿Cómo puedes estar segura de la redacción?
## Solución 
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Redaction gone wrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2024-04-04 17:09:32--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Labs.pdf         100%[====================================================================================>]  34.10K  --.-KB/s    in 0.04s   

2024-04-04 17:09:32 (785 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Redaction gone wrong]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf                                  
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Redaction gone wrong]
└─$ ls
Financialcopia.txt  Financial_Report_for_ABC_Labs.pdf  Financial_Report_for_ABC_Labs.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Desktop/EXP2/EXP2Pt2/Redaction gone wrong]
└─$ nano Financial_Report_for_ABC_Labs.txt

## Contraseña obtenida 
## Notas 
Aprendí mediante la herrmienta pdftotext a manipular archivos con está extensión a poder obtener datos de pdf a convertirlos a texto y finalmente se observa que podemos obtener datos muy intersantes. 
## Referencias
https://ubunlog.com/pdftotext-convierte-pdf-texto/
