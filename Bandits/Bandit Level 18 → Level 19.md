## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
La contraseña para el siguiente nivel se almacena en un archivo Léame en el directorio de inicio. Desafortunadamente, alguien ha modificado .bashrc para cerrar tu sesión cuando inicias sesión con SSH.
## Datos de usuario

Usuario: bandit18 bandit.labs.overthewire.org
contraseña: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
## Solución 
robert@DESKTOP-M9VOEL3:~ssh -l bandit18 bandit.labs.overthewire.org -p 2220 /bin/bash
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
whoami
bandit18
ls
readme
ls -la
total 24
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r-----  1 bandit19 bandit18 3794 Oct  5 06:19 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
-rw-r-----  1 bandit19 bandit18   33 Oct  5 06:19 readme
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
## Contraseña obtenida en este nivel 
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
## Notas 
Mediante un bash pudimos acceder a nuestro password 