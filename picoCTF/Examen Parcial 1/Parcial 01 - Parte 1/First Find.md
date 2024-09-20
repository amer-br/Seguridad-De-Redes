## Objetivo
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/502/files.zip)

## Solución
```bash
amer_br_-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/502/files.zip
--2024-09-11 05:40:58--  https://artifacts.picoctf.net/c/502/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: 'files.zip'

files.zip                                                  100%[=======================================================================================================================================>]   3.81M  --.-KB/s    in 0.02s   

2024-09-11 05:40:58 (230 MB/s) - 'files.zip' saved [3995553/3995553]

amer_br_-picoctf@webshell:~$ ls
README.txt  files.zip
amer_br_-picoctf@webshell:~$ unzip files.zip
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8   
amer_br_-picoctf@webshell:~$ ls
README.txt  files  files.zip
amer_br_-picoctf@webshell:~$ cd files
amer_br_-picoctf@webshell:~/files$ ls
13771.txt.utf-8  14789.txt.utf-8  acceptable_books  adequate_books  satisfactory_books
amer_br_-picoctf@webshell:~/files$ find -r uber-secret.txt
find: unknown predicate `-r'
amer_br_-picoctf@webshell:~/files$ find uber 
find: 'uber': No such file or directory
amer_br_-picoctf@webshell:~/files$ find -name uber-secret.txt
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
amer_br_-picoctf@webshell:~/files$ cd ^C
amer_br_-picoctf@webshell:~/files$ cd ./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
amer_br_-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ ls
uber-secret.txt
amer_br_-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas adicionales
**find -name** - sirve para buscar un archivo en una carpeta por su nombre
## Referencias
