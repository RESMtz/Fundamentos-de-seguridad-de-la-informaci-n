## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

La contraseña para el siguiente nivel se almacena en el archivo data.txt, que contiene datos codificados en base64.
## Datos de acceso 
Usuario:
ssh bandit10@bandit.labs.overthewire.org
Contraseña:
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
## Solución 
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
## Contraseña obtenida en este nivel 
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
## Notas 
El comando base64 -d nos permite visualizar de forma decodificada alguna información en algún archivo.
