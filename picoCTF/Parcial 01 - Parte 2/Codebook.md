

## Objetivo
Run the Python script `code.py` in the same directory as `codebook.txt`.
- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)
## Solución
```bash
amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2024-09-09 19:02:51--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.29, 3.167.183.84, 3.167.183.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.29|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                      100%[=============================================>]   1.25K  --.-KB/s    in 0s      

2024-09-09 19:02:51 (444 MB/s) - 'code.py' saved [1278/1278]

amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2024-09-09 19:03:03--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.29, 3.167.183.84, 3.167.183.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.29|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                 100%[=============================================>]      27  --.-KB/s    in 0s      

2024-09-09 19:03:04 (5.35 MB/s) - 'codebook.txt' saved [27/27]

amer_br_-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt
amer_br_-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```