## Objetivo
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/133/capture.flag.pcap)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ ls                         
capture.flag.pcap
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ file capture.flag.pcap 
capture.flag.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ xdg-open capture.flag.pcap 
```
![[Pasted image 20241026092331.png]]
Exportamos el paquete de bytes del paquete 57
```bash
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ ls
capture.flag.pcap  file.des3  file.txt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/Eavesdrop]
└─$ cat file.txt
picoCTF{nc_73115_411_5786acc3} 
```
## Notas adicionales
## Referencias
