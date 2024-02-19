## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Solución 
También puedes buscar en todo el sistema con el comando find de Linux. Sin embargo, debido al gran número de archivos y a la posible jerarquía profunda de directorios, esto puede llevar mucho tiempo. Para **buscar en todo el sistema**, utilizamos una barra diagonal “/” como ruta de acceso al directorio:
```
find / <search_parameter>
```
En este caso se usa del siguiente modo: 
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -type f
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -type f
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/polkit-1/localauthority’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/root’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
/var/lib/dpkg/info/bandit7.password
find: ‘/var/log’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/apparmor/30d07b40.0’: Permission denied
find: ‘/var/cache/apparmor/a4dd844e.0’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/tmp’: Permission denied
find: ‘/var/snap/lxd/common/lxd’: Permission denied
find: ‘/var/crash’: Permission denied
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/3707150/fdinfo/9’: No such file or directory
find: ‘/proc/3707152/task/3707152/fdinfo/6’: No such file or directory
find: ‘/proc/3707152/fdinfo/5’: No such file or directory
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/drifter8/chroot’: Permission denied
find: ‘/home/drifter6/data’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/lost+found’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/run/chrony’: Permission denied
find: ‘/run/user/11018’: Permission denied
find: ‘/run/user/11029’: Permission denied
find: ‘/run/user/8004’: Permission denied
find: ‘/run/user/11026’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/8001’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/screen/S-bandit23’: Permission denied
find: ‘/run/screen/S-bandit25’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/multipath’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/credentials/systemd-sysusers.service’: Permission denied
find: ‘/run/systemd/propagate’: Permission denied
find: ‘/run/systemd/unit-root’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
bandit6@bandit:~$ ls -l
total 0
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
## Contraseña obtenida en este nivel 
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
## Notas 
