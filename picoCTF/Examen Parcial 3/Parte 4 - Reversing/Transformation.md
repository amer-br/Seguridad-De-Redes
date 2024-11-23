## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/a757282979af14ab5ed74f0ed5e2ca95/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/transformation]
└─$ cat enc          
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彤㔲挶戹㍽                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/e3/transformation]
└─$ python 
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc = open("enc").read()
>>> enc
'灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彤㔲挶戹㍽'
>>> print(hex(ord(enc[0])))
0x7069
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"), end='')
... 
7069636f4354467b31365f626974735f696e73743334645f6f665f385f64353263366239337d>>> 
```
Transformamos de hex a ascii, dando como flag: picoCTF{16_bits_inst34d_of_8_d52c6b93}
![[Pasted image 20241116192230.png]]