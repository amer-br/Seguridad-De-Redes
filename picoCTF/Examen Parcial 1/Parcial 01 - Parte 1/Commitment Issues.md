## Objetivo
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/136/challenge.zip)
## Solución
```bash
amer_br_-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amer_br_-picoctf@webshell:~$ cd drop-in/
amer_br_-picoctf@webshell:~/drop-in$ ls
message.txt
amer_br_-picoctf@webshell:~/drop-in$ cat message.txt 
TOP SECRET
amer_br_-picoctf@webshell:~/drop-in$ git log

amer_br_-picoctf@webshell:~/drop-in$ git checkout 87b85d7dfb839b077678611280fa023d76e017b8
Note: switching to '87b85d7dfb839b077678611280fa023d76e017b8'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 87b85d7 create flag
amer_br_-picoctf@webshell:~/drop-in$ ls
message.txt
amer_br_-picoctf@webshell:~/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_ea83ff2a}
```
## Notas adicionales
**git checkout** - Sirve para mover el árbol de trabajo

