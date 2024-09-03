## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**
## Datos de acceso al nivel
Bandit15
Contraseña: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

## Solución
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 18C712B3C9DB408662C6B61176DE2A85882AFAB00963CA7E9FEB5A749205F1E4
    Session-ID-ctx:
    Resumption PSK: EF0D655D0BB0979FC89429DFC7BE10C1DD0D499E464C443FC60CC5D86561DD54ADD7A57FC7ACE91AE5CEEC14EBB92D54
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - 85 af 39 64 3b b8 1b 51-8f 1d 8f 02 b0 19 06 46   ..9d;..Q.......F
    0020 - a4 f8 6c f7 ef e3 07 03-af de cb 36 12 3e 7e 0c   ..l........6.>~.
    0030 - e0 6e aa c3 ac ba 54 25-c0 29 e4 c1 d1 d6 fe cf   .n....T%.)......
    0040 - 23 e2 77 63 44 e6 a3 5d-4c db 06 71 c5 28 13 15   #.wcD..]L..q.(..
    0050 - 2b c8 b5 77 b1 ab cd cb-cf 5c 5c ee 07 9e f6 c5   +..w.....\\.....
    0060 - f6 a3 73 57 17 71 ff 24-46 9a b1 0f 32 36 09 89   ..sW.q.$F...26..
    0070 - 5c f7 77 b0 3c 2f 28 02-2f 69 8c 24 e4 c5 b1 cc   \.w.</(./i.$....
    0080 - 53 f1 c0 a4 1a 3c 8d 07-71 3c 03 ab 03 6b 8c ed   S....<..q<...k..
    0090 - ae 60 9b c9 ea 86 d0 1f-5a c7 7d 2a fa 4b c8 c6   .`......Z.}*.K..
    00a0 - e3 01 c3 e4 59 81 e6 42-94 57 fe 91 9d 73 b7 e3   ....Y..B.W...s..
    00b0 - 9d 2a 06 51 5c a3 95 d1-d8 6c df 1a 1a 1e 1b 21   .*.Q\....l.....!
    00c0 - 57 0d 0c bc 0f c5 fe bc-a6 a8 f5 83 f0 3a 0e 01   W............:..
    00d0 - c5 db 57 d2 58 c6 87 23-07 c4 c6 57 51 d5 31 d3   ..W.X..#...WQ.1.

    Start Time: 1724986963
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: E2D15749F578FC3EDE39DD9F7DC25FBB753A8E1108F0F10545F30C306A640BFF
    Session-ID-ctx:
    Resumption PSK: 41C798E9E0787E7DC0A5C4B222433AABA0BE001450FB451C808163B13E79AE93FB19839008F1C605BD0148927357F679
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - 8e a5 02 ba e8 76 3f 91-51 f7 3b 50 5f ee c5 2a   .....v?.Q.;P_..*
    0020 - 65 1e 32 df cb 71 cb 6a-bb 69 2d 4f 8c 59 c7 9d   e.2..q.j.i-O.Y..
    0030 - e0 15 4e fa 08 50 f5 3b-60 a2 a8 77 a9 15 74 36   ..N..P.;`..w..t6
    0040 - 56 af 13 35 e7 7c 24 49-41 38 06 7b 54 4f ed d4   V..5.|$IA8.{TO..
    0050 - ba d3 ad 5d cc 3a d2 f1-6b 48 d8 fb 80 3f 1a ac   ...].:..kH...?..
    0060 - 74 f6 f2 8b e4 97 02 34-f3 32 26 03 ef ca b0 0d   t......4.2&.....
    0070 - bc 96 df c4 df 62 d2 f6-3d 39 d0 ae 45 78 26 81   .....b..=9..Ex&.
    0080 - 0c 9a f9 0b 8b 1d a4 51-60 22 e6 c6 7f 72 eb 4b   .......Q`"...r.K
    0090 - e2 89 99 d8 80 36 b0 6e-e4 e1 6b 37 97 4a 55 f3   .....6.n..k7.JU.
    00a0 - ba 26 e1 39 1d 6d 0a ac-d6 d6 b6 a2 ae cf 34 32   .&.9.m........42
    00b0 - f4 f6 0f 90 a3 a8 e4 8e-92 8a 45 eb 52 6c e0 d7   ..........E.Rl..
    00c0 - ae 59 04 5d ca cf 60 b0-73 a1 aa 30 c7 bb 50 f7   .Y.]..`.s..0..P.
    00d0 - 0c a6 d4 85 f4 06 98 e2-0b b3 d5 f6 5b d9 2a 9c   ............[.*.

    Start Time: 1724986963
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
```
## Notas adicionales
**`openssl s_client`**: Inicia una herramienta cliente de OpenSSL que permite establecer conexiones SSL/TLS a un servidor, simulando el comportamiento de un cliente SSL/TLS.
**`-connect localhost:30001`**: Especifica el destino de la conexión. En este caso, se conecta a `localhost` en el puerto `30001` usando SSL/TLS. Puedes sustituir `localhost` por cualquier otro nombre de host o dirección IP.
**`-ign_eof`**: Esta opción le dice a `openssl s_client` que ignore la señal EOF (End of File) de la entrada estándar (stdin). Esto significa que aunque se envíe una señal EOF, la sesión seguirá activa hasta que el servidor cierre la conexión o se cierre manualmente.

**ssl/tls** - es un protocolo de ocmunicación generalmente usado en sitios web(https)
**ncat** - es una herramienta similar a netacat pero con otras ventajas como conectar a puertos ssl

## Referencias