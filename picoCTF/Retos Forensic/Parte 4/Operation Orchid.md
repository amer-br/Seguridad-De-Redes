## Objetivo

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ fls -o 0000411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ icat -o 0000411648 disk.flag.img 1782
Salted__�ށ��e��B�J▒�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ icat -o 0000411648 disk.flag.img 1782 > flag.txt.enc
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ file flag.txt.enc                  
flag.txt.enc: openssl enc'd data with salted password
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ icat -o 0000411648 disk.flag.img 1875               
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40F758F3B37F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ cat flag.txt   
(b������4�D��U˫����O�����v�                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
4067E263A47F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic]
└─$ cat flag.txt
picoCTF{h4un71ng_p457_5113beab} 
```
## Notas adicionales
## Referencias
