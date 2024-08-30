## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
bandit11
Contraseña: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
## Solución
#### Opción 1
```bash
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
#### Opción 2
```bash
bandit11@bandit:~$ python3
Python 3.12.3 (main, Apr 10 2024, 05:33:47) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode("Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4", "ROT13")
'The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4'
```
#### Opción 3
Usando cyberchef
![[Pasted image 20240829211745.png]]


## Notas adicionales
**ROT13** Rota los caracteres 13 veces en el alfabeto.
## Referencias
[Rot13](https://en.wikipedia.org/wiki/ROT13)