## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel
bandit05
Contraseña: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
## Solución
```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
bandit5@bandit:~/inhere$ find -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd maybehere07
bandit5@bandit:~/inhere/maybehere07$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere07$ cat file2
cat: file2: No such file or directory
bandit5@bandit:~/inhere/maybehere07$ ls -la
total 56
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 .
drwxr-x--- 22 root bandit5 4096 Jul 17 15:57 ..
-rwxr-x---  1 root bandit5 3663 Jul 17 15:57 -file1
-rwxr-x---  1 root bandit5 3065 Jul 17 15:57 .file1
-rw-r-----  1 root bandit5 2488 Jul 17 15:57 -file2
-rw-r-----  1 root bandit5 1033 Jul 17 15:57 .file2
-rwxr-x---  1 root bandit5 3362 Jul 17 15:57 -file3
-rwxr-x---  1 root bandit5 1997 Jul 17 15:57 .file3
-rwxr-x---  1 root bandit5 4130 Jul 17 15:57 spaces file1
-rw-r-----  1 root bandit5 9064 Jul 17 15:57 spaces file2
-rwxr-x---  1 root bandit5 1022 Jul 17 15:57 spaces file3
bandit5@bandit:~/inhere/maybehere07$ cat ./.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG            
```
## Notas adicionales
find        Busca un archivo con las características que especifíques
-type f    Indica que sólo se busquen archivos regulares
-size 1033c    Indica el tamaño del archivo a buscar, la c indica que el tamaño está dado en bytes
## Referencias