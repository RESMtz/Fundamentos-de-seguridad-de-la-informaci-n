## Descripción del reto
El nombre del juego es [velocidad](https://www.youtube.com/watch?v=8piqd2BWeGI). ¿Eres lo suficientemente rápido para resolver este problema y mantenerlo por encima de las 50 mph? [necesidad de la velocidad](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Pistas 
¿Cuál es la clave final?
## Solución 
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ chmod +x need-for-speed` 
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ ./need-for-speed` 
`Keep this thing over 50 mph!`
============================

`Creating key...`
`Not fast enough. BOOM!`
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ objdump -D need-for-speed -M intel | grep '<main>:' -A20`
`000000000000091a <main>:`
 `91a:   55                      push   rbp`
 `91b:   48 89 e5                mov    rbp,rsp`
 `91e:   48 83 ec 10             sub    rsp,0x10`
 `922:   89 7d fc                mov    DWORD PTR [rbp-0x4],edi`
 `925:   48 89 75 f0             mov    QWORD PTR [rbp-0x10],rsi`
 `929:   b8 00 00 00 00          mov    eax,0x0`
 `92e:   e8 a5 ff ff ff          call   8d8 <header>`
 `933:   b8 00 00 00 00          mov    eax,0x0`
 `938:   e8 f2 fe ff ff          call   82f <set_timer>`
 `93d:   b8 00 00 00 00          mov    eax,0x0`
 `942:   e8 36 ff ff ff          call   87d <get_key>`
 `947:   b8 00 00 00 00          mov    eax,0x0`
 `94c:   e8 5b ff ff ff          call   8ac <print_flag>`
 `951:   b8 00 00 00 00          mov    eax,0x0`
 `956:   c9                      leave`
 `957:   c3                      ret`
 `958:   0f 1f 84 00 00 00 00    nop    DWORD PTR [rax+rax*1+0x0]`
 `95f:   00` 

`0000000000000960 <__libc_csu_init>:`
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ sudo apt install gdb`   
`[sudo] password for kali:` 
`Reading package lists... Done`
`Building dependency tree... Done`
`Reading state information... Done`
`The following additional packages will be installed:`
  `libbabeltrace1 libc-bin libc-dev-bin libc-devtools libc-l10n libc6 libc6-dbg`
  `libc6-dev libc6-i386 libdebuginfod-common libdebuginfod1 libipt2`
  `libsource-highlight-common libsource-highlight4v5 locales`
`Suggested packages:`
  `gdb-doc gdbserver glibc-doc libnss-nis libnss-nisplus`
`The following NEW packages will be installed:`
  `gdb libbabeltrace1 libc6-dbg libdebuginfod-common libdebuginfod1 libipt2`
  `libsource-highlight-common libsource-highlight4v5`
`The following packages will be upgraded:`
  `libc-bin libc-dev-bin libc-devtools libc-l10n libc6 libc6-dev libc6-i386`
  `locales`
`8 upgraded, 8 newly installed, 0 to remove and 574 not upgraded.`
`Need to get 23.9 MB of archives.`
`After this operation, 24.8 MB of additional disk space will be used.`
`Do you want to continue? [Y/n] y`
`Get:1 http://kali.download/kali kali-rolling/main amd64 libc6-i386 amd64 2.37-15 [2,460 kB]`
`Get:13 http://kali.darklab.sh/kali kali-rolling/main amd64 libsource-highlight-common all 3.1.9-4.2 [77.4 kB]`
`Get:14 http://http.kali.org/kali kali-rolling/main amd64 libsource-highlight4v5 amd64 3.1.9-4.2+b4 [324 kB]`
`Get:2 http://kali.download/kali kali-rolling/main amd64 libc-devtools amd64 2.37-15 [54.6 kB]`
`Get:3 http://kali.download/kali kali-rolling/main amd64 libc6-dev amd64 2.37-15 [1,906 kB]`
`Get:4 http://kali.download/kali kali-rolling/main amd64 libc-dev-bin amd64 2.37-15 [46.9 kB]`
`Get:5 http://kali.download/kali kali-rolling/main amd64 libc6 amd64 2.37-15 [2,750 kB]`
`Get:6 http://kali.download/kali kali-rolling/main amd64 libc-bin amd64 2.37-15 [602 kB]`
`Get:7 http://kali.download/kali kali-rolling/main amd64 libdebuginfod-common all 0.190-1 [22.3 kB]`
`Get:8 http://kali.download/kali kali-rolling/main amd64 libc-l10n all 2.37-15 [709 kB]`
`Get:9 http://kali.download/kali kali-rolling/main amd64 locales all 2.37-15 [3,908 kB]`
`Get:10 http://http.kali.org/kali kali-rolling/main amd64 libbabeltrace1 amd64 1.5.11-3+b3 [176 kB]`
`Get:11 http://http.kali.org/kali kali-rolling/main amd64 libdebuginfod1 amd64 0.190-1+b1 [28.3 kB]`
`Get:12 http://kali.download/kali kali-rolling/main amd64 libipt2 amd64 2.0.6-1 [43.2 kB]`
`Get:15 http://kali.download/kali kali-rolling/main amd64 gdb amd64 13.2-1 [3,968 kB]`
`Get:16 http://kali.download/kali kali-rolling/main amd64 libc6-dbg amd64 2.37-15 [6,815 kB]`
`Fetched 23.9 MB in 5s (4,634 kB/s)`       
`Preconfiguring packages ...`
`(Reading database ... 411443 files and directories currently installed.)`
`Preparing to unpack .../libc6-i386_2.37-15_amd64.deb ...`
`Unpacking libc6-i386 (2.37-15) over (2.37-12) ...`
`Preparing to unpack .../libc-devtools_2.37-15_amd64.deb ...`
`Unpacking libc-devtools (2.37-15) over (2.37-12) ...`
`Preparing to unpack .../libc6-dev_2.37-15_amd64.deb ...`
`Unpacking libc6-dev:amd64 (2.37-15) over (2.37-12) ...`
`Preparing to unpack .../libc-dev-bin_2.37-15_amd64.deb ...`
`Unpacking libc-dev-bin (2.37-15) over (2.37-12) ...`
`Preparing to unpack .../libc6_2.37-15_amd64.deb ...`
`Unpacking libc6:amd64 (2.37-15) over (2.37-12) ...`
`Setting up libc6:amd64 (2.37-15) ...`
`(Reading database ... 411443 files and directories currently installed.)`
`Preparing to unpack .../libc-bin_2.37-15_amd64.deb ...`
`Unpacking libc-bin (2.37-15) over (2.37-12) ...`
`Setting up libc-bin (2.37-15) ...`
`Selecting previously unselected package libdebuginfod-common.`
`(Reading database ... 411443 files and directories currently installed.)`
`Preparing to unpack .../0-libdebuginfod-common_0.190-1_all.deb ...`
`Unpacking libdebuginfod-common (0.190-1) ...`
`Preparing to unpack .../1-libc-l10n_2.37-15_all.deb ...`
`Unpacking libc-l10n (2.37-15) over (2.37-12) ...`
`Preparing to unpack .../2-locales_2.37-15_all.deb ...`
`Unpacking locales (2.37-15) over (2.37-12) ...`
`Selecting previously unselected package libbabeltrace1:amd64.`
`Preparing to unpack .../3-libbabeltrace1_1.5.11-3+b3_amd64.deb ...`
`Unpacking libbabeltrace1:amd64 (1.5.11-3+b3) ...`
`Selecting previously unselected package libdebuginfod1:amd64.`
`Preparing to unpack .../4-libdebuginfod1_0.190-1+b1_amd64.deb ...`
`Unpacking libdebuginfod1:amd64 (0.190-1+b1) ...`
`Selecting previously unselected package libipt2.`
`Preparing to unpack .../5-libipt2_2.0.6-1_amd64.deb ...`
`Unpacking libipt2 (2.0.6-1) ...`
`Selecting previously unselected package libsource-highlight-common.`
`Preparing to unpack .../6-libsource-highlight-common_3.1.9-4.2_all.deb ...`
`Unpacking libsource-highlight-common (3.1.9-4.2) ...`
`Selecting previously unselected package libsource-highlight4v5:amd64.`
`Preparing to unpack .../7-libsource-highlight4v5_3.1.9-4.2+b4_amd64.deb ...`
`Unpacking libsource-highlight4v5:amd64 (3.1.9-4.2+b4) ...`
`Selecting previously unselected package gdb.`
`Preparing to unpack .../8-gdb_13.2-1_amd64.deb ...`
`Unpacking gdb (13.2-1) ...`
`Selecting previously unselected package libc6-dbg:amd64.`
`Preparing to unpack .../9-libc6-dbg_2.37-15_amd64.deb ...`
`Unpacking libc6-dbg:amd64 (2.37-15) ...`
`Setting up libc-l10n (2.37-15) ...`
`Setting up libdebuginfod-common (0.190-1) ...`
`Setting up libdebuginfod1:amd64 (0.190-1+b1) ...`
`Setting up locales (2.37-15) ...`
`Generating locales (this might take a while)...`
  `en_US.UTF-8... done`
`Generation complete.`
`Setting up libsource-highlight-common (3.1.9-4.2) ...`
`Setting up libc6-dbg:amd64 (2.37-15) ...`
`Setting up libipt2 (2.0.6-1) ...`
`Setting up libbabeltrace1:amd64 (1.5.11-3+b3) ...`
`Setting up libc6-i386 (2.37-15) ...`
`Setting up libc-dev-bin (2.37-15) ...`
`Setting up libsource-highlight4v5:amd64 (3.1.9-4.2+b4) ...`
`Setting up libc-devtools (2.37-15) ...`
`Setting up gdb (13.2-1) ...`
`Setting up libc6-dev:amd64 (2.37-15) ...`
`Processing triggers for libc-bin (2.37-15) ...`
`Processing triggers for man-db (2.12.0-3) ...`
`Processing triggers for kali-menu (2023.4.7) ...`
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ gdb`                                                     
`GNU gdb (Debian 13.2-1) 13.2`
`Copyright (C) 2023 Free Software Foundation, Inc.`
`License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>`
`This is free software: you are free to change and redistribute it.`
`There is NO WARRANTY, to the extent permitted by law.`
`Type "show copying" and "show warranty" for details.`
`This GDB was configured as "x86_64-linux-gnu".`
`Type "show configuration" for configuration details.`
`For bug reporting instructions, please see:`
`<https://www.gnu.org/software/gdb/bugs/>.`
`Find the GDB manual and other documentation resources online at:`
    `<http://www.gnu.org/software/gdb/documentation/>.`

`For help, type "help".`
`Type "apropos word" to search for commands related to "word".`
`(gdb) exit`
                                                                                 
`┌──(kali㉿kali)-[~/Desktop/Retos picoCTF/Need For Speed]`
`└─$ gdb need-for-speed` 
`GNU gdb (Debian 13.2-1) 13.2`
`Copyright (C) 2023 Free Software Foundation, Inc.`
`License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>`
`This is free software: you are free to change and redistribute it.`
`There is NO WARRANTY, to the extent permitted by law.`
`Type "show copying" and "show warranty" for details.`
`This GDB was configured as "x86_64-linux-gnu".`
`Type "show configuration" for configuration details.`
`For bug reporting instructions, please see:`
`<https://www.gnu.org/software/gdb/bugs/>.`
`Find the GDB manual and other documentation resources online at:`
    `<http://www.gnu.org/software/gdb/documentation/>.`

`For help, type "help".`
`Type "apropos word" to search for commands related to "word"...`
`Reading symbols from need-for-speed...`
`(No debugging symbols found in need-for-speed)`
`(gdb) info functions` 
`All defined functions:`

`Non-debugging symbols:`
`0x00000000000005d8  _init`
`0x0000000000000600  putchar@plt`
`0x0000000000000610  puts@plt`
`0x0000000000000620  alarm@plt`
`0x0000000000000630  __sysv_signal@plt`
`0x0000000000000640  exit@plt`
`0x0000000000000650  __cxa_finalize@plt`
`0x0000000000000660  _start`
`0x0000000000000690  deregister_tm_clones`
`0x00000000000006d0  register_tm_clones`
`0x0000000000000720  __do_global_dtors_aux`
`0x0000000000000760  frame_dummy`
`0x000000000000076a  decrypt_flag`
`0x00000000000007f1  calculate_key`
`0x000000000000080e  alarm_handler`
`0x000000000000082f  set_timer`
`0x000000000000087d  get_key`
`0x00000000000008ac  print_flag`
`0x00000000000008d8  header`
`0x000000000000091a  main`
`0x0000000000000960  __libc_csu_init`
`0x00000000000009d0  __libc_csu_fini`
`0x00000000000009d4  _fini`
`(gdb) set disassembly-flavor intel`
`(gdb) disassemble main`
`Dump of assembler code for function main:`
   `0x000000000000091a <+0>:     push   rbp`
   `0x000000000000091b <+1>:     mov    rbp,rsp`
   `0x000000000000091e <+4>:     sub    rsp,0x10`
   `0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi`
   `0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi`
   `0x0000000000000929 <+15>:    mov    eax,0x0`
   `0x000000000000092e <+20>:    call   0x8d8 <header>`
   `0x0000000000000933 <+25>:    mov    eax,0x0`
   `0x0000000000000938 <+30>:    call   0x82f <set_timer>`
   `0x000000000000093d <+35>:    mov    eax,0x0`
   `0x0000000000000942 <+40>:    call   0x87d <get_key>`
   `0x0000000000000947 <+45>:    mov    eax,0x0`
   `0x000000000000094c <+50>:    call   0x8ac <print_flag>`
   `0x0000000000000951 <+55>:    mov    eax,0x0`
   `0x0000000000000956 <+60>:    leave`
   `0x0000000000000957 <+61>:    ret`
`End of assembler dump.`
`(gdb) break main`
`Breakpoint 1 at 0x91e`
`(gdb) info breakpoints` 
`Num     Type           Disp Enb Address            What`
`1       breakpoint     keep y   0x000000000000091e <main+4>`
`(gdb) run`
`Starting program: /home/kali/Desktop/Retos picoCTF/Need For Speed/need-for-speed` 
`[Thread debugging using libthread_db enabled]`
`Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".`

`Breakpoint 1, 0x000055555540091e in main ()`
`(gdb) disassemble main`
`Dump of assembler code for function main:`
   `0x000055555540091a <+0>:     push   rbp`
   `0x000055555540091b <+1>:     mov    rbp,rsp`
`=> 0x000055555540091e <+4>:     sub    rsp,0x10`
   `0x0000555555400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi`
   `0x0000555555400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi`
   `0x0000555555400929 <+15>:    mov    eax,0x0`
   `0x000055555540092e <+20>:    call   0x5555554008d8 <header>`
   `0x0000555555400933 <+25>:    mov    eax,0x0`
   `0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>`
   `0x000055555540093d <+35>:    mov    eax,0x0`
   `0x0000555555400942 <+40>:    call   0x55555540087d <get_key>`
   `0x0000555555400947 <+45>:    mov    eax,0x0`
   `0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>`
   `0x0000555555400951 <+55>:    mov    eax,0x0`
   `0x0000555555400956 <+60>:    leave`
   `0x0000555555400957 <+61>:    ret`
`End of assembler dump.`
`(gdb) call (int) get_key()`
`Creating key...`

`Finished`
`$1 = 9`
`(gdb)` 
`Creating key...`
`Finished`
`$2 = 9`
`(gdb) call (int) print_flag()`
`Printing flag:`
`PICOCTF{Good job keeping bus #190ca38b speeding along!}`
`$3 = 56`
`(gdb)` 

## Contraseña obtenida 
PICOCTF{Good job keeping bus #190ca38b speeding along!}

## Notas
Es importante saber usar el gdb para poder observar lo que viene siendo nuestro archivo. Para poder saber como se va ejecutando nuestro archivo, ahora si que digamos paso a paso para poder observar nuestras funciones. 
## Referencias 
https://lihuen.linti.unlp.edu.ar/index.php/C%C3%B3mo_usar_GDB