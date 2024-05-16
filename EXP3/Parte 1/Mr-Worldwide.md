## Descripción del reto
Un músico nos dejó un [mensaje](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). ¿Qué significa?

## Pistas 
No hay.
## Solución 
Descargamos nuestro archivo y podemos ver que nos arroja una serie de coordenadas :
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}

Ahora reacomodamos y buscamos coordenada a coordenada. 

picoCTF{
	(35.028309, 135.753082) Kyoto, Japón 
	(46.469391, 30.740883)  Odesa, Ucrania 
	(39.758949, -84.191605) Dayton Ohio, Estados Unidos
	(41.015137, 28.979530)  Istambul Faith, Turquia 
	(24.466667, 54.366669) Abu Dahi, Emiratos arabes
	(3.140853, 101.693207) Kuala Lumpur, Territorio Federal de Kuala Lumpur, Malasia
	(9.005401, 38.763611) Adís Abeba, Etiopía
	(-3.989038, -79.203560)  Loja, Ecuador
	(52.377956, 4.897070)  Ámsterdam, Países Bajo
	(41.085651, -73.858467) Sleepy Hollow, Nueva York, EE. UU. 
	(57.790001, -152.407227)  Kodiak, Alaska, EE. UU
	(31.205753, 29.924526) Alexandria Governorate , Egipto
	} 
Se observa que nos da un nombre de un lugar. Podemos observar que la palbra entonces seria: 
KODIAKALASKA
Esto tomando la primer letra de los lugares de las coordenas.
## Contraseña obtenida 
picoCTF{KODIAK_ALASKA}
## Notas 
Es importante saber que hasta en una herramienta tan básica como lo es el maps de Google nos puede ayudar muchisimo, incluso para poder obtener información de muy básica como lo fue en este reto.
## Referencias 
https://www.google.com.mx/maps/preview
