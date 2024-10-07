## Objetivo
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Solución
En consola
```bash
┌──(kali㉿kali)-[~]
└─$ curl -I http://mercury.picoctf.net:28916/index.php 
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
Content-type: text/html; charset=UTF-8

```

![[Pasted image 20240925103120.png]]
## Notas adicionales
## Referencias
[Métodos de solicitud HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
