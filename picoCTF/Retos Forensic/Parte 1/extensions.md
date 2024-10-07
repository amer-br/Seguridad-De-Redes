## Objetivo
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/extensions]
└─$ ls
flag.txt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/extensions]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/extensions]
└─$ mv flag.txt flag.png

```
![[Pasted image 20241002110445.png]]

## Referencias
[Lista de firma de archivos](https://en.wikipedia.org/wiki/List_of_file_signatures)
