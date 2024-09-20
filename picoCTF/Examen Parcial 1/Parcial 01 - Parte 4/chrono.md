## Objetivo
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.

## Solución
```bash
picoplayer@challenge:~$ ls -la
total 12
drwxr-xr-x 1 picoplayer picoplayer   20 Sep 14 06:01 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Sep 14 06:01 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
```
## Notas adicionales
**cat /etc/crontab** en Linux muestra el contenido del archivo de configuración del **sistema de cron**. El archivo `/etc/crontab` es un archivo especial que contiene tareas programadas que se ejecutan automáticamente a intervalos regulares por el servicio **cron**.