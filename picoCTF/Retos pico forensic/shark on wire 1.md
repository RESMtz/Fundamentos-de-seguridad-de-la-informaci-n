## Descripción del reto
Encontramos esta captura de paquete. Recuperar la bandera.
URL: https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
## Pistas 
1.- Intente utilizar una herramienta como Wireshark
2.- ¿Qué son las corrientes?

## Solución 
1.- Comenzamos descargando y posicionando el archivo correspondiente. 
2.- Vemos que es un archivo con la extensión pcap, lo cual nos indica que es una captura.
3.- Procedemos a abrir el wireshark, el cual es un programa que nos permite ver un muestreo de los paquetes.
4.- Una vez dentro, damos clic en file, después buscamos nuestro archivo descargado.
5.- Una vez abierto hay que ubicar algún paquete que tenga el protocolo de UDP y le damos clic derecho y en el boton que dice "follow".
6.- Una vez ahí nos abre una ventana emergente la cual nos muestra cierta información. Damos clic en la esquina inferior derecha, en este caso yo elegí el paquete 4, hasta el 6 me arrojo el flag.

## Contraseña obtenida 
picoCTF{StaT31355_636f6e6e}
## Notas 
Aquí con referencia en lo visto en clases pude obtener un acceso y uso del software wireshark el cual nos permite analizar y hacer un muestreo que nos permite ver el estado y contenido de los paquetes.
## Referencias 
Aquí no utilice sitios de terceros.