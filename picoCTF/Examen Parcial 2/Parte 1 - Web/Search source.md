## Objetivo
The developer of this website mistakenly left an important artifact in the website source, can you find it?

Additional details will be available after launching your challenge instance.

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/web/bookmarklet]
└─$ ls
saturn.picoctf.net:59195
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/web/bookmarklet]
└─$ grep -R pico saturn.picoctf.net:59195 
saturn.picoctf.net:59195/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7} **/

```

