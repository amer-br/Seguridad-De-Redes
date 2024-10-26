## Objetivo
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/crypto/information]
└─$ exiftool cat.jpg 
ExifTool Version Number         : 12.76
File Name                       : cat.jpg

...

Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/information]
└─$ exiftool cat.jpg | grep License
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/information]
└─$ exiftool cat.jpg | grep License | sed -e 's/.*: //'
cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/information]
└─$ exiftool cat.jpg | grep License | sed -e 's/.*: //'|base64 -d
picoCTF{the_m3tadata_1s_modified} 
```
## Notas adicionales
## Referencias
