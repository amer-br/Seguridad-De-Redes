## Objetivo
Fix the syntax error in the Python script to print the flag.
[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)
## Solución
El error estaba en que al comparar usaba "=" en vez de ==
```bash
amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/4/fixme2.py
--2024-09-09 19:19:33--  https://artifacts.picoctf.net/c/4/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.84, 3.167.183.74, 3.167.183.29, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.84|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                    100%[=============================================>]   1.00K  --.-KB/s    in 0s      

2024-09-09 19:19:34 (84.7 MB/s) - 'fixme2.py' saved [1029/1029]

amer_br_-picoctf@webshell:~$ ls
README.txt  fixme2.py
amer_br_-picoctf@webshell:~$ python fixme2.py 
  File "/home/amer_br_-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
amer_br_-picoctf@webshell:~$ nano fixme2.py 
amer_br_-picoctf@webshell:~$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```

