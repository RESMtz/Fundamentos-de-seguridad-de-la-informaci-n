## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

Hay un repositorio git en ssh://bandit29-git@localhost/home/bandit29-git/repo a través del puerto 2220. La contraseña para el usuario bandit29-git es la misma que para el usuario bandit29.

Clona el repositorio y busca la contraseña para el siguiente nivel.

## Datos de usuario del nivel anterior

Usuario: ssh bandit29@bandit.labs.overthewire.org -p 2220
Contraseña: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución 
1.- Creamos un directorio y cambiamos a el 
`bandit29@bandit:~$ mkdir /tmp/band29`
`bandit29@bandit:~$ cd /tmp/band29`
2.- Clonamos nuevamente nuestro repositorio:
`bandit29@bandit:/tmp/band29$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo`
`Cloning into 'repo'...`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit29/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).`
                         `_                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit29-git@localhost's password:`
`remote: Enumerating objects: 16, done.`
`remote: Counting objects: 100% (16/16), done.`
`remote: Compressing objects: 100% (11/11), done.`
`remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0`
`Receiving objects: 100% (16/16), done.`
`Resolving deltas: 100% (2/2), done.`
3.- Cambiamos nuevamente al directorio donde hicimos nuestra clonación:
`bandit29@bandit:/tmp/band29$ cd repo`
`bandit29@bandit:/tmp/band29/repo$ ls`
`README.md`
4.- Ejectuamos el archivo que esta ahí 

`bandit29@bandit:/tmp/band29/repo$ cat README.md`
`Bandit Notes`
`Some notes for bandit30 of bandit.`

 `credentials`

- `username: bandit30`
- `password: <no passwords in production!>`
5.- Se observa que no hay contraseñas entonces ponemos el comando git log para poder ver el historial:

`bandit29@bandit:/tmp/band29/repo$ git log`
`commit 4364630b3b27c92aff7b36de7bb6ed2d30b60f88 (HEAD -> master, origin/master, origin/HEAD)`
`Author: Ben Dover <noone@overthewire.org>`
`Date:   Thu Oct 5 06:19:43 2023 +0000`

    `fix username`

`commit fca34ddb7d1ff1f78df36538252aea650b0b040d`
`Author: Ben Dover <noone@overthewire.org>`
`Date:   Thu Oct 5 06:19:43 2023 +0000`

    `initial commit of README.md`
   6.- Aplicamos un git checkout para poder cambiarnos de rama:
    
`bandit29@bandit:/tmp/band29/repo$ git checkout fca34ddb7d1ff1f78df36538252aea650b0b040d`
`Note: switching to 'fca34ddb7d1ff1f78df36538252aea650b0b040d'.`

`You are in 'detached HEAD' state. You can look around, make experimental`
`changes and commit them, and you can discard any commits you make in this`
`state without impacting any branches by switching back to a branch.`

`If you want to create a new branch to retain commits you create, you may`
`do so (now or later) by using -c with the switch command. Example:`

  `git switch -c <new-branch-name>`

`Or undo this operation with:`

  `git switch -`

`Turn off this advice by setting config variable advice.detachedHead to false`

`HEAD is now at fca34dd initial commit of README.md`
7.- Finalmente aplicamos ls para poder ver los archivos y nuevamente ejecutamos
`bandit29@bandit:/tmp/band29/repo$ ls`
`README.md`
`bandit29@bandit:/tmp/band29/repo$ cat REAME.md`
`cat: REAME.md: No such file or directory`
`bandit29@bandit:/tmp/band29/repo$ cat README.md`
`# Bandit Notes`
`Some notes for bandit30 of bandit.`

`## credentials`

`- username: bandit29`
`- password: <no passwords in production!>`
8.- Se observa que no genera contraseñas entonces aplicamos un branch que este nos auxilia mediante listas y poder observar todas las ramas o carpetas que estan en el directorio:
`bandit29@bandit:/tmp/band29/repo$ git branch -a`
`* (HEAD detached at fca34dd)`
  `master`
  `remotes/origin/HEAD -> origin/master`
  `remotes/origin/dev`
  `remotes/origin/master`
  `remotes/origin/sploits-dev`
  9.- Nuevamente hacemos un cambio a través de git checkout con nuestros repositorios obtenidos anteriormente, ya adentro aplicamos ls para ver los archivos disponibles y así finalmente ejecutamos nuestro cat al archivo.
`bandit29@bandit:/tmp/band29/repo$ git checkout remotes/origin/dev`
`Previous HEAD position was fca34dd initial commit of README.md`
`HEAD is now at 1d160de add data needed for development`
`bandit29@bandit:/tmp/band29/repo$ ls`
`code  README.md`
`bandit29@bandit:/tmp/band29/repo$ cat README.md`
`# Bandit Notes`
`Some notes for bandit30 of bandit.`

`## credentials`

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
## Contraseña obtenida en este nivel 
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
## Notas 
Aquí en este nivel aprendí a usar y que importancia tiene el Branch, debido que es importante tener siempre un listado de las cosas, ya que podemos obtener el problema desde una carpeta raíz. 
## Referencias 
https://app.aluracursos.com/forum/topico-branch-235494
https://git-scm.com/docs/git-log
https://www.hostinger.mx/tutoriales/comandos-de-git
