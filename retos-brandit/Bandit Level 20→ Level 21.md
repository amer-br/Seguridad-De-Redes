## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
bandit20
**Contraseña**: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
## Solución
```bash
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ nc -lnvp 1819 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO &
[1] 3137757
bandit20@bandit:~$ Listening on 0.0.0.0 1819

bandit20@bandit:~$ ./suconnect 1819
Connection received on 127.0.0.1 59172
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
[1]+  Done                    nc -lnvp 1819 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```
## Notas adicionales
**&** - si agregamos un simbolo de estos al final de un comando, lo estamos enviando al segundo plano (background)
**jobs** - muestra qué comandos están en el segundo plano
**fg** - saca un proceso o comando del segundo plano
## Referencias
