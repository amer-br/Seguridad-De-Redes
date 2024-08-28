## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso al nivel
bandit06
Contraseña:HWasnPhtq9AVKe0dmk45nxy20cvUa6EG 

## Solución
```bash
bandit6@bandit:~$ ls
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
## Notas adicionales
**`find /`**: Inicia la búsqueda en el directorio raíz `/` y en todos sus subdirectorios.
**`-user bandit7`**: Filtra los archivos que pertenecen al usuario `bandit7`
**`-group bandit6`**: Filtra los archivos que pertenecen al grupo `bandit6`.
**`-size 33c`**: Filtra los archivos que tienen exactamente 33 bytes de tamaño
**`2>/dev/null`**: Redirige cualquier mensaje de error (como permisos denegados) a `/dev/null`, lo que significa que esos mensajes no se mostrarán en la terminal.
## Referencias