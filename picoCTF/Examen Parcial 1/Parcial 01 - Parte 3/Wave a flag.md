## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) has extraordinarily helpful information...

## Solución
```bash
amer_br_-picoctf@webshell:~$ ls
README.txt  warm
amer_br_-picoctf@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=7b3da2efd83a2b9154697b6c7f6474042e1fd033, with debug_info, not stripped
amer_br_-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
amer_br_-picoctf@webshell:~$ chmod 777 warm
amer_br_-picoctf@webshell:~$ ls
README.txt  warm
amer_br_-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
amer_br_-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```
## Notas adicionales
**chmod 777** - Para darle todos los permisos a un archivo.
## Referencias