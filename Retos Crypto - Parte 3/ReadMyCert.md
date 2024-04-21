## Descripción del reto
¿Qué tal si lo llevamos a una aventura para explorar las solicitudes de firma de certificados?
Eche un vistazo a este archivo CSR  [aqui](https://artifacts.picoctf.net/c/421/readmycert.csr).

## Pistas 
Descargue la solicitud de firma del certificado e intente leerla.
## Solución 
1. Comenzamos descargando nuestro archivo en su directorio
2. Previamente descargado, lo abrimos y vemos que es un texto cifrado.
3. Lo podemos decifrar mediante una herramienta online. 
4. [Herramienta](https://www.sslshopper.com/csr-decoder.html)
5. Una vez ahí ingresamos el texto y vemos que nos arroja un campo que dice "Common Name:** picoCTF{read_mycert_3aa80090}"
## Contraseña obtenida 
picoCTF{read_mycert_3aa80090}
## Notas 
Este nivel fue sencillo de resolver, debido a que la herramienta proporcionada nos fue de gran ayuda.
## Referencias 
https://www.sslshopper.com/csr-decoder.html