## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!

## Solución
```bash
mer_br_-picoctf@webshell:~$ ls
README.txt  ltdis.sh  static
amer_br_-picoctf@webshell:~$ chmod 777 static
amer_br_-picoctf@webshell:~$ ls
README.txt  ltdis.sh  static
amer_br_-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
amer_br_-picoctf@webshell:~$ ls
-static.ltdis.x86_64.txt  README.txt  ltdis.sh  static
amer_br_-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_ae0b3ef2}
```
