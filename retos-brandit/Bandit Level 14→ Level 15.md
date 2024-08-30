## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel
bandit14
Contraseña: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

## Solución
```bash
bandit14@bandit:~$ ls
bandit14@bandit:~$
bandit14@bandit:~$ which nc
/usr/bin/nc
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```
## Notas adicionales
**nc** Es una herramienta que permite conectarse a un host remoto, también podemos abrir un puerto
**nc localhost 30000**
	localhost - es el host o la maquina a la que me quiero conectar
		30000 - es el puerto
## Referencias