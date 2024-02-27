## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

Hay un repositorio git en ssh://bandit27-git@localhost/home/bandit27-git/repo a través del puerto 2220. La contraseña para el usuario bandit27-git es la misma que para el usuario bandit27.

Clona el repositorio y busca la contraseña para el siguiente nivel.
## Datos de usuario del nivel anterior

Usuario: ssh bandit27@bandit.labs.overthewire.org -p 2220
Contraseña: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución 
1.- Primeramente debemos crear un directorio temporal, debido a que si intentamos clonar el repositorio de github directamente, nos dará los permisos necesarios y accedemos a este directorio temporal:
`bandit27@bandit:~$ mktemp -d`
`/tmp/tmp.jAQP6kjI34`
`bandit27@bandit:~$ cd /tmp/tmp.jAQP6kjI34`
2.- Una vez ahí dentro procedemos ahora si a clonar nuestro repositorio:

`bandit27@bandit:/tmp/tmp.jAQP6kjI34$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo`
`Cloning into 'repo'...`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit27/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).`
                         `_                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit27-git@localhost's password:`
`remote: Enumerating objects: 3, done.`
`remote: Counting objects: 100% (3/3), done.`
`remote: Compressing objects: 100% (2/2), done.`
`remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0`
`Receiving objects: 100% (3/3), done.`
3.- Ahora hacemos nuevamente un cambio al repositorio donde muestra un archivo, dicho archivo lo ejectuamos con CAT
`bandit27@bandit:/tmp/tmp.jAQP6kjI34$ cd repo`
`bandit27@bandit:/tmp/tmp.jAQP6kjI34/repo$ ls`
`README`
`bandit27@bandit:/tmp/tmp.jAQP6kjI34/repo$ cat README`

The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
## Contraseña obtenida en este nivel 
AVanL161y9rsbcJIsFHuw35rjaOM19nR
## Notas 
Este nivel fue sencillo debido a que pudimos aplicar conocimiento previo, y mediante la creación de directorios fue sencillo poder usar el mktemp, que es aquel comando que permite crear carpetas o directorios temporales. 

## Referencias 
https://manpages.ubuntu.com/manpages/trusty/es/man3/mktemp.3.html#:~:text=La%20funci%C3%B3n%20mktemp()%20genera,el%20nombre%20no%20est%C3%A9%20repetido.
https://www.w3big.com/es/linux/linux-comm-mktemp.html#gsc.tab=0
https://www.hostinger.mx/tutoriales/comandos-de-git
