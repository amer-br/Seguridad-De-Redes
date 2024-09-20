## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
## Solución
```bash
amer_br_-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2024-09-09 17:25:02--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                      100%[=============================================>] 757.84K  --.-KB/s    in 0.007s  

2024-09-09 17:25:02 (111 MB/s) - 'strings' saved [776032/776032]

amer_br_-picoctf@webshell:~$ ls
README.txt  strings
amer_br_-picoctf@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=0cdedfba33422d235dba8c90e00fb77b235f1ff8, not stripped
amer_br_-picoctf@webshell:~$ strings -n 15 strings| grep pico
picoCTF{5tRIng5_1T_7f766a23}
```
## Notas adicionales
**strings** - permite obtener las cadenas de texto que hay en un archivo binario.
## Referencias
