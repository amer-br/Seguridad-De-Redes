## Objetivo
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/crypto]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_7142uwv9}
```

Lo metemos a cyberchef
![[Pasted image 20241023114433.png]]
## Notas adicionales
## Referencias
