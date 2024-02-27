## Objetivo
There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

Clone the repository and find the password for the next level.

Hay un repositorio git en ssh://bandit28-git@localhost/home/bandit28-git/repo a través del puerto 2220. La contraseña para el usuario bandit28-git es la misma que para el usuario bandit28.

Clona el repositorio y busca la contraseña para el siguiente nivel.

## Datos de usuario del nivel anterior

Usuario: ssh bandit28@bandit.labs.overthewire.org -p 2220
Contraseña: AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solución 
1.- Como en el nivel anterior creamos un directorio pero está vez no es temporal:

`bandit28@bandit:/tmp$ mkdir bandit28`
`bandit28@bandit:/tmp$ cd bandit28`

2.- Una vez ahí procedemos a clonar nuevamente el repositorio mediante el comando git clone: 

`bandit28@bandit:/tmp/bandit28$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo`
`Cloning into 'repo'...`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit28/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).`
                         `_                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit28-git@localhost's password:`
`remote: Enumerating objects: 9, done.`
`remote: Counting objects: 100% (9/9), done.`
`remote: Compressing objects: 100% (6/6), done.`
`remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0`
`Receiving objects: 100% (9/9), done.`
`Resolving deltas: 100% (2/2), done.`
`bandit28@bandit:/tmp/bandit28$ cd repo`
3.- Una vez ahí hacemos un ls para ver que hay dentro:
`bandit28@bandit:/tmp/bandit28$ cd repo`
`bandit28@bandit:/tmp/bandit28/repo$ ls`
`README.md`
4.- Al ejectuar el archivo README.md nos arroja lo siguiente :

bandit28@bandit:/tmp/bandit28/repo$ cat README.md
 `Bandit Notes`
`Some notes for level29 of bandit.`
`credentials`

- `username: bandit29`
- `password: xxxxxxxxxx`
5.- Ejecutamos git log para poder mostrar el historial de los commits
`bandit28@bandit:/tmp/bandit28/repo$ git log`
`commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)`
`Author: Morla Porla <morla@overthewire.org>`
`Date:   Thu Oct 5 06:19:41 2023 +0000`

    `fix info leak`

`commit f08b9cc63fa1a4602fb065257633c2dae6e5651b`
`Author: Morla Porla <morla@overthewire.org>`
`Date:   Thu Oct 5 06:19:41 2023 +0000`

    `add missing data`

`commit a645bcc508c63f081234911d2f631f87cf469258`
`Author: Ben Dover <noone@overthewire.org>`
`Date:   Thu Oct 5 06:19:41 2023 +0000`

    `initial commit of README.md`

6.- Finalmente con el comando git checkout para poder cambiarnos a través de los commit:
`bandit28@bandit:/tmp/bandit28/repo$ git checkout f08b9cc63fa1a4602fb065257633c2dae6e5651b`
`Note: switching to 'f08b9cc63fa1a4602fb065257633c2dae6e5651b'.`

`You are in 'detached HEAD' state. You can look around, make experimental`
`changes and commit them, and you can discard any commits you make in this`
`state without impacting any branches by switching back to a branch.`

`If you want to create a new branch to retain commits you create, you may`
`do so (now or later) by using -c with the switch command. Example:`

  `git switch -c <new-branch-name>`

`Or undo this operation with:`

  `git switch -`

`Turn off this advice by setting config variable advice.detachedHead to false`

`HEAD is now at f08b9cc add missing data`
7.- Aplicamos ls y ejectuamos el archivo 
`bandit28@bandit:/tmp/bandit28/repo$ ls`
`README.md`
`bandit28@bandit:/tmp/bandit28/repo$ cat README.md`
 `Bandit Notes`
`Some notes for level29 of bandit.`
`credentials`

- `username: bandit29`
- `password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S`

`bandit28@bandit:/tmp/bandit28/repo$ client_loop: send disconnect: Broken pipe`

## Contraseña obtenida en este nivel 
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
## Notas 
Descubrí a usar el git checkout, ya que es aquel comando que permite hacer cambio de ramas, sin olvidar el git log que también me auxilio para poder observar nuestro historial de los commits, que fue de mucha ayuda.
## Referencias
https://www.hostinger.mx/tutoriales/comandos-de-git
https://git-scm.com/docs/git-checkout
https://git-scm.com/docs/git-log

