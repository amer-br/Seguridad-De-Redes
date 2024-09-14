## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

## Solución
```bash
mer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
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
amer_br_-picoctf@webshell:~$ ^C
amer_br_-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt
amer_br_-picoctf@webshell:~$ rm code.py
amer_br_-picoctf@webshell:~$ cat codebook.txt
azbycxdwevfugthsirjqkplomn
amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2024-09-09 19:07:11--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                 100%[=============================================>]   1.16K  --.-KB/s    in 0s      

2024-09-09 19:07:11 (443 MB/s) - 'convertme.py' saved [1189/1189]

amer_br_-picoctf@webshell:~$ ls
README.txt  convertme.py
amer_br_-picoctf@webshell:~$ python convertme.py 
If 91 is in decimal base, what is it in binary base?
Answer: 1011011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
```
## Notas adicionales
Usé un convertidor de decimal a binario para convertir el número 91.
## Referencias
[Decimal to Binary](https://www.rapidtables.com/convert/number/decimal-to-binary.html?x=91)