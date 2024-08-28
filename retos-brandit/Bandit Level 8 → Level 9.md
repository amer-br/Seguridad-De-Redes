## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.
## Datos de acceso al nivel
bandit8
Contraseña: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
## Solución
```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc -l data.txt
1001 data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
## Notas adicionales
**wc -l**     Se utiliza para contar el número de líneas en un archivo
**sort data.txt**    Se utiliza para ordenar las líneas de un archivo en orden alfabético y mostrar el resultado en la terminal.
**uniq -u**    Se utiliza para mostrar únicamente las líneas que son **únicas** (no repetidas) en un archivo

## Referencias