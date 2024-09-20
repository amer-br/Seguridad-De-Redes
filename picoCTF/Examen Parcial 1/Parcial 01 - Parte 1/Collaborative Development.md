## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)

## Solución
Vamos buscando cada parte de la bandera en las diferentes ramas
```bash
amer_br_-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amer_br_-picoctf@webshell:~$ cd drop-in/
amer_br_-picoctf@webshell:~/drop-in$ ls
flag.py
amer_br_-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")
amer_br_-picoctf@webshell:~/drop-in$ git branch
amer_br_-picoctf@webshell:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
amer_br_-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')amer_br_-picoctf@webshell:~/drop-in$ ^C
amer_br_-picoctf@webshell:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
amer_br_-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')amer_br_-picoctf@webshell:~/drop-in$ ^C
amer_br_-picoctf@webshell:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
amer_br_-picoctf@webshell:~/drop-in$ cat flag.py 
print("Printing the flag...")

print("w0rk_2c91ca76}")
```
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}

