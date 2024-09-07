## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
bandit31
**Contraseña:** fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
## Solución
Clonas el repositorio indicado en el objetivo
```bash
bandit31@bandit:/tmp/tmp.0s4I6fNknK$ ls -la
total 10816
drwx------    3 bandit31 bandit31     4096 Sep  7 17:23 .
drwxrwx-wt 7362 root     root     11063296 Sep  7 17:24 ..
drwxrwxr-x    3 bandit31 bandit31     4096 Sep  7 17:24 repo
bandit31@bandit:/tmp/tmp.0s4I6fNknK$ cd repo
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep  7 17:24 .
drwx------ 3 bandit31 bandit31 4096 Sep  7 17:23 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep  7 17:24 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep  7 17:24 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep  7 17:24 README.md
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ git .gitignore
git: '.gitignore' is not a git command. See 'git --help'.
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ git branch
* master
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ rm .gitignore
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ git add key.txt
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ git commit -m "Añadir llave"
[master da2d885] Añadir llave
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.0s4I6fNknK/repo$ git push
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 329 bytes | 329.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```
## Notas adicionales
**.gitignore**: es un archivo de configuración en Git que le dice al sistema de control de versiones qué archivos o directorios deben ser ignorados y no incluidos en el repositorio. Esto es útil para evitar que archivos temporales, archivos de configuración específicos del entorno o archivos que no deben ser versionados se añadan al repositorio.

## Referencias
