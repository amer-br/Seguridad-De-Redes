## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
bandit7
Contraseña: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
## Solución
```bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ ls -la
total 4108
drwxr-xr-x  2 root    root       4096 Jul 17 15:57 .
drwxr-xr-x 70 root    root       4096 Jul 17 15:58 ..
-rw-r--r--  1 root    root        220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root    root       3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit8 bandit7 4184396 Jul 17 15:57 data.txt
-rw-r--r--  1 root    root        807 Mar 31 08:41 .profile
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ wc -l
^C
bandit7@bandit:~$ grep millionth data.txt
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ grep -n milliont data.txt
86483:millionth dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
## Notas adicionales
**wc -l**  Cuenta las líneas que tiene un archivo de texto
**grep -n** El comando grep permite filtrar las lines de un archivo en base a un patrón
		-n indica a grep que muestre el numero de línea
## Referencias
