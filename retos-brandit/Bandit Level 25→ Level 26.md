## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

> NOTE: if you’re a Windows user and typically use Powershell to `ssh` into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.
## Datos de acceso al nivel
bandit25
**Contraseña:** iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

## Solución
```bash
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0

  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
--More--(66%)

PRESS V

 _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
"~/text.txt" [readonly] 6L, 258B  
:e /etc/bandit_pass/bandit26


For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       ~                                                                                                                       Vim: Caught deadly signal HUPreadonly] 1L, 33B                                                        1,1           All

Vim: Finished.
Connection to bandit.labs.overthewire.org closed.
```
## Notas adicionales
## Referencias