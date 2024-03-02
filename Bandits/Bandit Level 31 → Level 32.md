## Objetivo

There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level.

Hay un repositorio git en ssh://bandit31-git@localhost/home/bandit31-git/repo a través del puerto 2220. La contraseña para el usuario bandit31-git es la misma que para el usuario bandit31.

Clona el repositorio y busca la contraseña para el siguiente nivel.

## Datos de usuario del nivel anterior

Usuario: ssh bandit31@bandit.labs.overthewire.org -p 2220
Contraseña: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solución 
`bandit31@bandit:~$ mkdir /tmp/rsantos_bandit31`
`bandit31@bandit:~$ cd  /tmp/rsantos_bandit31`
`bandit31@bandit:/tmp/rsantos_bandit31$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo`
`Cloning into 'repo'...`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit31/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).`
                         `_                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit31-git@localhost's password:`
`remote: Enumerating objects: 4, done.`
`remote: Counting objects: 100% (4/4), done.`
`remote: Compressing objects: 100% (3/3), done.`
`remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0`
`Receiving objects: 100% (4/4), done.`
`bandit31@bandit:/tmp/rsantos_bandit31$ ls`
`repo`
`bandit31@bandit:/tmp/rsantos_bandit31$ cd repo`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$ ls`
`README.md`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$ cat README.md`
`This time your task is to push a file to the remote repository.`

`Details:`
    `File name: key.txt`
    `Content: 'May I come in?'`
    `Branch: master`

`bandit31@bandit:/tmp/rsantos_bandit31/repo$ nano key.txt`
`Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory`
`It is required for saving/loading search history or cursor positions.`

`bandit31@bandit:/tmp/rsantos_bandit31/repo$ ls -a`
`.  ..  .git  .gitignore  key.txt  README.md`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$ cat .gitignore`
`*.txt`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$  git add -f key.txt`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$ git commit -m "Upload key.txt"`
`[master 2cf96cb] Upload key.txt`
 `1 file changed, 1 insertion(+)`
 `create mode 100644 key.txt`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$ git push -u origin master`
`The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.`
`ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.`
`This key is not known by any other names`
`Are you sure you want to continue connecting (yes/no/[fingerprint])? yes`
`Could not create directory '/home/bandit31/.ssh' (Permission denied).`
`Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).`
`^[[6~                         _                     _ _ _`
                        `| |__   __ _ _ __   __| (_) |_`
                        `| '_ \ / _ | '_ \ / _ | | __|`
                        `| |_) | (_| | | | | (_| | | |_`
                        `|_.__/ \__,_|_| |_|\__,_|_|\__|`


                      `This is an OverTheWire game server.`
            `More information on http://www.overthewire.org/wargames`

`bandit31-git@localhost's password:`
`Enumerating objects: 4, done.`
`Counting objects: 100% (4/4), done.`
`Delta compression using up to 2 threads`
`Compressing objects: 100% (2/2), done.`
`Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.`
`Total 3 (delta 0), reused 0 (delta 0), pack-reused 0`
`remote: ### Attempting to validate files... ####`
`remote:`
`remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.`
`remote:`
`remote: Well done! Here is the password for the next level:`
`remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y`
`remote:`
`remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.`
`remote:`
`To ssh://localhost:2220/home/bandit31-git/repo`
 `! [remote rejected] master -> master (pre-receive hook declined)`
`error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'`
`bandit31@bandit:/tmp/rsantos_bandit31/repo$``
`
## Contraseña obtenida en este nivel 
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
## Referencias 
https://www.warp.dev/terminus/understanding-git-push-origin#:~:text=git%20push%20origin%20is%20a,a%20remote%20repository%20(origin).&text=origin%20is%20the%20conventional%20shorthand,repository%20provider)%20for%20your%20project.
https://www.atlassian.com/es/git/tutorials/syncing
https://git-scm.com/docs/git-commit