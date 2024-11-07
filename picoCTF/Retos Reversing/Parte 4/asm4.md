## Objetivo
What will asm4("picoCTF_a3112") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S)

## Solución
Editamos el código para que podamos ejecutarlo(lo llamamos chal.s):
```bash
.intel_syntax noprefix
.global asm4

asm4:
        push   ebp
        mov    ebp,esp
        push   ebx
        sub    esp,0x10
        mov    DWORD PTR [ebp-0x10],0x246
        mov    DWORD PTR [ebp-0xc],0x0
        jmp    asm4+27
        add    DWORD PTR [ebp-0xc],0x1
        mov    edx,DWORD PTR [ebp-0xc]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        test   al,al
        jne    asm4+23
        mov    DWORD PTR [ebp-0x8],0x1
        jmp    asm4+138
        mov    edx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    eax,DWORD PTR [ebp-0x8]
        lea    ecx,[eax-0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        mov    edx,eax
        mov    eax,DWORD PTR [ebp-0x10]
        lea    ebx,[edx+eax*1]
        mov    eax,DWORD PTR [ebp-0x8]
        lea    edx,[eax+0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
```

Creamos un programa en c en el que llamamos a la función con el parámetro indicado en el reto(llamado solve.c):
```bash
#include <stdio.h>

extern int asm4(const char *input);

int main() {
        printf("Flag: 0x%x\n", asm4("picoCTF_a3112"));
}
```

Ensamblamos el archivo `chal.s` a un objeto:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm4]
└─$ gcc -m32 -c chal.s -o chal.o
```

Compilamos y enlazamos `solve.c` y `chal.o`:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm4]
└─$ gcc -m32 solve.c chal.o -o solve
/usr/bin/ld: warning: chal.o: missing .note.GNU-stack section implies executable stack
/usr/bin/ld: NOTE: This behaviour is deprecated and will be removed in a future version of the linker
```

Al ejecutarlo nos muestra la flag:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm4]
└─$ ./solve
Flag: 0x1d0
```

