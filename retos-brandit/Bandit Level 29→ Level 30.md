## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
bandit29
**Contraseña:** 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

## Solución
```bash
bandit29@bandit:~$ mktemp -d
/tmp/tmp.8bxrUoKLds
bandit29@bandit:~$ cd /tmp/tmp.8bxrUoKLds
bandit29@bandit:/tmp/tmp.8bxrUoKLds$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.8bxrUoKLds$ ls
repo
bandit29@bandit:/tmp/tmp.8bxrUoKLds$ cd repo
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ ls
README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git log
commit efa5bd803f8335e5e5e9da5c4c7c876aefc9f8b4 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    fix username

commit 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git checkout 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
Note: switching to '5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 5a53eb8 initial commit of README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ ls
README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit29
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Sep  7 16:58 .
drwx------ 3 bandit29 bandit29 4096 Sep  7 16:56 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Sep  7 16:58 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Sep  7 16:58 README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git branch
* (HEAD detached at efa5bd8)
  master
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git checkout dev
Previous HEAD position was efa5bd8 fix username
branch 'dev' set up to track 'origin/dev'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ git log
commit eef534022d1ecc3b41d6de068501c4db4154b2c7 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    add data needed for development

commit 301cf80fd7d0012c519077fcc5e1568cda8e4b8e
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    add gif2ascii

commit efa5bd803f8335e5e5e9da5c4c7c876aefc9f8b4 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    fix username

commit 5a53eb83a43bac1f0b4e223e469b40ef68a4b6e6
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:31 2024 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ ls
code  README.md
bandit29@bandit:/tmp/tmp.8bxrUoKLds/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

## Notas adicionales
**git branch -r**: en Git muestra una lista de todas las **ramas remotas** del repositorio. Las ramas remotas son versiones del repositorio que están almacenadas en el servidor remoto (por ejemplo, en GitHub, GitLab, Bitbucket, etc.), y no necesariamente están presentes en tu copia local hasta que las traigas (fetch) o hagas un checkout de ellas.

**git branch:** Git te mostrará una lista de las ramas locales en tu repositorio. La rama en la que te encuentras actualmente estará precedida por un asterisco (`*`).

## Referencias
