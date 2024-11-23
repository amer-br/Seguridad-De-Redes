## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/BAO4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
```
- La función asigna un valor constante (654874) a una variable.
- Evalúa si ese valor es mayor o menor o igual a `10000`.
- Modifica el valor:
    - Resta `101` si es mayor (siempre será este caso en el ejemplo dado).
    - Suma `101` si es menor o igual (no aplica aquí).
- Retorna el valor resultante (654773).

```bash
>>> 0x9fe1a
654874
>>> 0x2710
10000
>>> 0x65
101
>>> 0x9fe1a - 0x65
654773

```
