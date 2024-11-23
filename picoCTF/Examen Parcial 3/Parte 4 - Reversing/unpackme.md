## Objetivo
Can you get the flag? Reverse engineer this [binary](https://artifacts.picoctf.net/c/203/unpackme-upx).

## Solución
```bash
__libc_freeres_ptrs
.comment
.note.stapsdt
                                                                                                
┌──(kali㉿kali)-[~/picoCTFretos/e3/unpackme]
└─$ python
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xb83cb
754635
>>> exit()
                                                                                                
┌──(kali㉿kali)-[~/picoCTFretos/e3/unpackme]
└─$ ./unpackme-upx                        
What's my favorite number? 754635
picoCTF{up><_m3_f7w_77ad107e}
```
