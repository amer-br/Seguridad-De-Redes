## Objetivo
## Datos de acceso al nivel
bandit32
**Contraseña**: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

## Solución
```bash
  Enjoy your stay!

WELCOME TO THE UPPERCASE SHELL
>> l
sh: 1: L: Permission denied
>> ls
sh: 1: LS: Permission denied
>> $shell
WELCOME TO THE UPPERCASE SHELL
>> $EUID
>> $0
$ export SHELL =/bin/bash
sh: 1: export: : bad variable name
$ export SHELL=/bin/bash
$ echo $SHELL
/bin/bash
$ $SHELL
bandit33@bandit:~$ cat /etc/bandit_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```
## Notas adicionales
Al usar ssh para acceder a la máquina, nos encontramos con un shell ligeramente diferente: `WELCOME TO THE UPPERCASE SHELL`. De modo que todo lo que escribimos parece estar en mayúsculas. Sin embargo, los comandos que hemos utilizado hasta ahora están todos en minúsculas y no funcionan. Lo único que está en mayúsculas en Linux son las variables. En concreto, la variable `$0`tiene una referencia a un shell. Puedes ver esto `echo $0`en tu máquina.

Esto nos permite salir del shell en mayúsculas y podemos usar comandos nuevamente.
## Referencias
