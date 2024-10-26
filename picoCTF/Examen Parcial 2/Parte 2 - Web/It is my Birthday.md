## Objetivo
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website. [http://mercury.picoctf.net:20277/](http://mercury.picoctf.net:20277/)

## Solución
Subimos dos archivos PDF diferentes
![[Pasted image 20241026165115.png]]
## Notas adicionales
It is now well-known that the crytographic hash function MD5 has been broken. In March 2005, Xiaoyun Wang and Hongbo Yu of Shandong University in China published an [article](http://www.infosec.sdu.edu.cn/paper/md5-attack.pdf) in which they describe an algorithm that can find two different sequences of 128 bytes with the same MD5 hash.
## Referencias
https://www.mscs.dal.ca/~selinger/md5collision/
