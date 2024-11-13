## Objetivo
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 60368`.

## Solución
Usamos este código:
```bash
from pwn import *
import binascii
r=remote("mercury.picoctf.net",60368)
print(r.recvuntil("n:"))
n=int(r.recvline())
print(n)
print(r.recvuntil("e:"))
e=int(r.recvline())
print(e)
print(r.recvuntil("ciphertext:"))
c=int(r.recvline())
print(c)
print(r.recvuntil("to decrypt:"))
# We will send c*2^e. It decrypts to c^d*2^(ed) = 2*c^d
# It is different, and will decrypt to plaintext*2
r.sendline(str(pow(2,e,n)*c))
print(r.recvuntil("you go:"))
p2=int(r.recvline())
print(p2)
print(p2//2)
st="{:x}".format(p2//2)
print(binascii.unhexlify(st))
```

```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/NoPaddinNoProblem]
└─$ python nopad.py      
[◣] Opening connection to mercury.picoctf.net on port 60368: Trying 18.189.20[+] Opening connection to mercury.picoctf.net on port 60368: Done
/home/kali/picoCTFretos/e3/NoPaddinNoProblem/nopad.py:4: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
...
290275030195850039473456618367455885069965748851278076756743720446703314517401359267322769037469251445384569347680788099965
b'picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_3279013}'
[*] Closed connection to mercury.picoctf.net port 60368
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/e3/NoPaddinNoProblem]
```
## Notas adicionales
## Referencias
