## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
bandit30
**Contraseña:** qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
## Solución
Primero clonamos el repositorio que se indica en el objetivo
```bash
bandit30@bandit:/tmp/tmp.kn2LByuWAP$ ls -la
total 10816
drwx------    3 bandit30 bandit30     4096 Sep  7 17:09 .
drwxrwx-wt 7348 root     root     11063296 Sep  7 17:11 ..
drwxrwxr-x    3 bandit30 bandit30     4096 Sep  7 17:10 repo
bandit30@bandit:/tmp/tmp.kn2LByuWAP$ cd repo
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Sep  7 17:10 .
drwx------ 3 bandit30 bandit30 4096 Sep  7 17:09 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Sep  7 17:10 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Sep  7 17:10 README.md
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ git log
commit 60410f42e05023128098dc1f6991c75e6ae02e47 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:34 2024 +0000

    initial commit of README.md
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.kn2LByuWAP/repo$ git show secret
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```
## Notas adicionales
**git tag:** en Git se utiliza para crear, listar y gestionar **etiquetas** (tags). Las etiquetas son referencias que apuntan a un commit específico y generalmente se usan para marcar puntos importantes en la historia del repositorio, como versiones de software o lanzamientos.

**git show:** seguido de un nombre de objeto, como `secret`, intentará mostrar información sobre ese objeto específico (ya sea le nombre de un tag, un commit o  de una rama).

## Referencias
