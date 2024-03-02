## Objetivo


## Solución 
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 18 10:53:16 2024 GMT; NotAfter: Feb 18 10:54:16 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEcjY6OTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjE4MTA1MzE2WhcNMjQwMjE4MTA1NDE2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCz
TX1NLedZhpQfXiWbWWD2BlNYjANpj+TnzUOI9ZbKJnOQJAbFfWZLA6No7XOStgje
+RPIoAHrX42G95VDfWtRms+qCsCTlUaS9291dZJQ3iOjBIE+PvmRcGdUlFJXDYa6
E61L2DKLbb8YSAnSuUPG3K7CtdxJpA5DpCBCmHEA9t5gZ5HGo9Gt9Kay9lhApX78
ocytwwHG15LplXI6LQB3ykhyCAcfljR3azd90T83dz7kLyM7yIMt60k1kemuX6RW
qSvkCvxmckRFoQPjwKZUopGLlhcC58Kb2xlwEGK+9j/ibBRkmEdBkOOeb5pJol7K
Wkd9LdG0nTWrggni7EKbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCA
j53OECoyjZMkHINZj35xk2kKQc9Jj9XjoCE0HlooUWd1ETik/2TkIbdWenozDrgH
10Jqmu/zAEhQkfFALBXCR7Vo0319yvR3rlnC2TdzMeBeUQ/n6ivPsCCL6SF8UTWT
XZJoTEfmp+Ma4zup/mEs23uO/FQ0J3LmSgICtXzPCA09M/ffj2UgTENdTHDltQxl
nQpzF+U40+bg/2PQ83XOTQJbZVbU2FnP/MitSYycxemLJXzbdsIxQhQy0VmTY73E
ZFemHVTbzEzcsCJRak4AyPZ9Zpi2uozHA8r1PqtnDzsN5FBFwuJxCuc+F8QeHh9e
QoyfsotkA6BO0LBqWNvE
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 204DB209BD641757081C3B6F70D85207A3A8E5F363AF26A1C9D9F72B4EE5E3F4
    Session-ID-ctx:
    Resumption PSK: 5D2BB35F91124C580B2B202853C062582BA42B652681DCB690811C6157FBDFD1FAA9742CBE338F23819D529CBA60EE0F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - c0 17 9e 89 f7 f6 79 dd-cb cb a3 56 2b f2 19 99   ......y....V+...
    0020 - 5d 10 d6 79 b2 30 9b 87-5e 24 06 e2 4a a8 23 7d   ]..y.0..^$..J.#}
    0030 - 71 56 0c 8d e3 9f 9a c5-22 61 8e 00 5d c2 11 57   qV......"a..]..W
    0040 - a8 0c 44 91 ba 95 7c 08-ef d5 b1 2a e8 49 bd 08   ..D...|....*.I..
    0050 - 70 d6 bc c4 10 ed dc 9c-73 c6 d7 b4 29 11 72 60   p.......s...).r`
    0060 - c2 d2 f6 e4 d0 64 1d ae-b7 c9 2d 82 63 a3 67 fc   .....d....-.c.g.
    0070 - 37 58 a6 70 d2 76 4d 7f-95 13 bc 34 d1 cf 0c 8b   7X.p.vM....4....
    0080 - 3b df 6d c1 ee a7 f7 cd-a2 71 c3 92 5b 30 9a 4b   ;.m......q..[0.K
    0090 - a0 d5 09 4f 08 41 c1 76-2c 20 ed b8 f6 80 5e 44   ...O.A.v, ....^D
    00a0 - ba 76 1b f4 44 a2 ad fd-c2 8c 8f e0 fe 5c 61 f4   .v..D........\a.
    00b0 - b5 70 1d c2 97 ae 24 b4-54 20 dd f9 a0 0e 69 89   .p....$.T ....i.
    00c0 - c0 13 17 82 bb fd 94 5e-26 36 56 c5 85 ea 7d 44   .......^&6V...}D

    Start Time: 1708370574
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 62D575FAC26543B0C672C9C746CD40BCC4CA944D516A4872CAEE184AE3F845FC
    Session-ID-ctx:
    Resumption PSK: C3B095BB4F6A466C7E8B8D8B9AF1FC340C33EB17F4FF9FA25798ABA3875362F2175768F7618332C1B1413584BDADA706
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - 80 1d 19 58 af cb 28 2b-fe 0b 7b d8 2c 6f b1 f9   ...X..(+..{.,o..
    0020 - b5 11 d7 7b ce f9 1b c4-b4 7b b8 55 0a 34 5c 8e   ...{.....{.U.4\.
    0030 - df bd d1 ed 50 c8 04 7d-a6 c7 82 d1 0d ab 58 c1   ....P..}......X.
    0040 - e7 8f bb 6b ca a7 cb 78-a7 b4 4d d1 50 56 08 75   ...k...x..M.PV.u
    0050 - 0a f7 29 d3 f9 33 44 42-e1 6b 1d 1e c0 80 04 3c   ..)..3DB.k.....<
    0060 - 2a 44 72 64 8f 9f 76 92-c8 25 d7 12 5c 3c 50 61   *Drd..v..%..\<Pa
    0070 - 07 7d 45 75 23 dd 55 3a-ed 88 e0 9d 1c c1 b9 39   .}Eu#.U:.......9
    0080 - be 8a 82 44 4d c3 97 45-8a 8f e9 22 de 21 3b 18   ...DM..E...".!;.
    0090 - d7 84 5d 8e ea 4a 58 d7-5e b5 0a ef 7b e2 fc f8   ..]..JX.^...{...
    00a0 - c2 c0 2c 35 c9 01 5d 05-d9 33 a1 ca 11 75 e2 1f   ..,5..]..3...u..
    00b0 - 09 2b 59 63 12 1a 93 3f-b5 b0 d0 7c 8f cf 88 bf   .+Yc...?...|....
    00c0 - 43 ce 43 50 19 fe fd 8f-9e 93 7c 07 ad 6a 5b b0   C.CP......|..j[.

    Start Time: 1708370574
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
## Contraseña obtenida en este nivel 
JQttfApK4SeyHwDlI9SXGR50qclOAil1
## Notas 
Mediante los certificados también podemos obtener información bastante importante ya que nos para este nivel fue funamental para poder obtener la password, aprendí a usar el comando openssl s_client -connect localhost: -número de puerto para poder establecer una comunicación con cierto numero de puerto que cuenta con características se SSL.