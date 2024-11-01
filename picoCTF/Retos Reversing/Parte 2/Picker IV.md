## Objetivo
Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 60519` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV).

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/picker4]
└─$ objdump -D picker-IV| grep win
000000000040129e <win>:
  4012d2:       75 16                   jne    4012ea <win+0x4c>
  4012f9:       eb 1a                   jmp    401315 <win+0x77>
  401319:       75 e0                   jne    4012fb <win+0x5d>
                                                                             
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/picker4]
└─$ nc saturn.picoctf.net 60519
Enter the address in hex to jump to, excluding '0x': 40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}

```
