## Descripción del reto
Tenemos varias páginas ocultas. ¿Puedes encontrar el que tiene la bandera?
El sitio web se está ejecutando aquí.
## Pistas 
folders folders folders
## Solución 
Primero comenzamos inspeccionando la página la cual  nos arroja un código en html el cual tiene disitintas referencias para ello cambie nuestra liga original agregando /secret/
http://saturn.picoctf.net:64727/secret/
Despues de esto analizamos la página nuevamente y nos pone de referencia la palabra /hidden y lo ponemos en el link:
https://saturn.picoctf.net/secret/hidden
Despues nuevamente inspeccionamos y nos vamos a la pestaña de fuentes y obtenemos otra referencia la sustituimos otra vez
http://saturn.picoctf.net:64727/secret/hidden/superhidden/
Finalmente otra vez inspeccionamos la página y asi obtenemos el código la sifguiente linea:
`<h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>`
Y aquí se obtiene la bandera

## Contraseña obtenida 
picoCTF{succ3ss_@h3n1c@10n_790d2615}
## Notas 
Es importante saber inspeccionar a día de hoy las páginas, ya que muchas veces no sabemos lo que tienen de contenido dentro. 
## Referencias 
No necesite fuentes externas. 
