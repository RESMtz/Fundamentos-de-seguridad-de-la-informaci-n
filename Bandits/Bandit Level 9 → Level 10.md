
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
La contraseña para el siguiente nivel se almacena en el archivo data.txt en una de las pocas cadenas legibles por humanos, precedida por varios caracteres "=".

## Solución 
bandit9@bandit:~$ strings data.txt
Nos arroja lo que viene siendo las lineas del archivo
pero para ello como queremos las lineas que unicamente tengan el caracter '='
entonces nos auxiliamos de los comandos strings y grep

bandit9@bandit:~$ strings data.txt | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
## Contraseña obtenida en este nivel 
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
## Nota