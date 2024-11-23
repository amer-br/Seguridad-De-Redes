## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Solución
Hacemos un archivo llamado sol.c con el siguiente código:
```bash
#include <stdio.h>

int main(void)

{
  int local_10;
  int local_c;
  
  local_c = 0x1e0da;
  for (local_10 = 0; local_10 < 0x25f; local_10 = local_10 + 1) {
    local_c = local_c + local_10;
  }
  printf("%i", local_c);
}
```

```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/GDB2]
└─$ gcc sol.c -o sol
                                              
┌──(kali㉿kali)-[~/picoCTFretos/e3/GDB2]
└─$ ls
debugger0_b  sol  sol.c
                                              
┌──(kali㉿kali)-[~/picoCTFretos/e3/GDB2]
└─$ ./sol  
307019 
```
Dando la flag picoCTF{307019}