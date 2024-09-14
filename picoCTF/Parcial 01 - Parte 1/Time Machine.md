## Objetivo
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/161/challenge.zip)
## Solución
```bash
amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/161/challenge.zip
amer_br_-picoctf@webshell:~$ ls
README.txt  challenge.zip
amer_br_-picoctf@webshell:~$ unzip challenge.zip
amer_br_-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amer_br_-picoctf@webshell:~$ cd drop-in/
amer_br_-picoctf@webshell:~/drop-in$ ls
message.txt
amer_br_-picoctf@webshell:~/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...amer_br_-picoctf@webshell:~/drop-in$ 
amer_br_-picoctf@webshell:~/drop-in$ git log
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}
```
## Notas adicionales
**git log** : Te muestra el historial de commits.
## Referencias
