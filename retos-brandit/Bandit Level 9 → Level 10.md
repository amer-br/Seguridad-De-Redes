## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
bandit9
Contraseña: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
## Solución
```bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ cat data.txt | strings | grep ==
\a!;========== the
========== passwordf
========== isc
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
## Notas adicionales
**`cat data.txt`**: Este comando muestra el contenido del archivo `data.txt` en la terminal.
**`strings`**: Este comando extrae y muestra las secuencias de caracteres legibles (es decir, texto) de un archivo binario o de cualquier archivo en general.
**`grep ==`**: El comando `grep` busca y muestra líneas que coinciden con un patrón específico.
## Referencias