## Objetivo
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)

## Solución
```bash
amer_br_-picoctf@webshell: unzip big-file-file.zip
amer_br_-picoctf@webshell:~$ ls
README.txt  big-zip-files  big-zip-files.zip
amer_br_-picoctf@webshell:~$ cd big-zip-files
amer_br_-picoctf@webshell:~/big-zip-files$ grep -r "pico"
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```
## Notas adicionales
## Referencias
