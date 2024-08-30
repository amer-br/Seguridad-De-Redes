## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
bandit10
Contraseña: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
## Solución
#### Opción 1

```bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
#### Opción 2
Usando cyberchef
![[Pasted image 20240829211402.png]]
#### Opción 3
```bash
bandit10@bandit:~$ python3
Python 3.12.3 (main, Apr 10 2024, 05:33:47) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode("VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==")
b'The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr\n'
```

## Notas adicionales
**base64** codifica un mensaje en base 64
**base64 -d** descodifica un mensaje en base64
## Referencias
[Base64](https://en.wikipedia.org/wiki/Base64)
[Cyberchef](https://gchq.github.io/CyberChef/)