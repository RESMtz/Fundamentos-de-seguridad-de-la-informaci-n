## Objetivo


There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

Clone the repository and find the password for the next level.

Hay un repositorio git en ssh://bandit30-git@localhost/home/bandit30-git/repo a través del puerto 2220. La contraseña para el usuario bandit30-git es la misma que para el usuario bandit30.

Clona el repositorio y busca la contraseña para el siguiente nivel.
## Datos de usuario del nivel anterior

Usuario: ssh bandit30@bandit.labs.overthewire.org -p 2220
Contraseña: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución 
1.- Comenzamos creando nuestro directorio:
`bandit30@bandit:~$ mkdir /tmp/bandit30_rsantos`
`bandit30@bandit:~$ cd /tmp/bandit30_rsantos`
2.- Una vez ahí procedemos a clonar el repositorio:
`bandit30@bandit:/tmp/bandit30_rsantos$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo`
`Cloning into 'repo'...`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit30/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).`
                         `_                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit30-git@localhost's password:`
`remote: Enumerating objects: 4, done.`
`remote: Counting objects: 100% (4/4), done.`
`remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0`
`Receiving objects: 100% (4/4), done.`

`bandit30@bandit:/tmp/bandit30_rsantos$ cd repo`
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ ls`
`README.md`
3.- Una vez ahí ejectuamos el comando cat al archivo para ver que hay adentro
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ cat README.md`
`just an epmty file... muahaha`
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ git log`
`commit d39631d73f786269b895ae9a7b14760cbf40a99f (HEAD -> master, origin/master, origin/HEAD)`
`Author: Ben Dover <noone@overthewire.org>`
`Date:   Thu Oct 5 06:19:45 2023 +0000`

    `initial commit of README.md`
4.- Aplicamos un branch para poder hacer un listado
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ git branch -a`
* `master`
  `remotes/origin/HEAD -> origin/master`
  `remotes/origin/master`
  5.- Finalmente aplicamos un git tag, el cual nos permite hacer un listado de etiquetas como se observa hay una etiqueta secret oculta 
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ git tag`
`secret`
5.- Aplicamos git show para poder mostrar la información de nuestra etiqueta.
`bandit30@bandit:/tmp/bandit30_rsantos/repo$ git show secret`
`OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt`


## Contraseña obtenida en este nivel 
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Notas 
Aquí en este nivel pude descubrir el uso de dos nuevos comandos para mí, el tag y el show ya que son comandos muy utiles dentro del comando GIT, que nos permite hacer muchas tareas, el aplicar estos comandos para las etiquetas y mostrar sus caracteristicas es algo que nos ayuda bastante, sobretodo si se quiere obtener una flag.
## Referencias
https://git-scm.com/docs/git-show
https://git-scm.com/book/es/v2/Fundamentos-de-Git-Etiquetado

