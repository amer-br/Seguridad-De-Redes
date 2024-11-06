## Objetivo
What does asm1(0x2e0) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/f1c2358ff7d1e9386e41552c549cf2f6/test.S)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm1]
└─$ file test.S 
test.S: ASCII text
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm1]
└─$ cat test.S     
asm1:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   cmp    DWORD PTR [ebp+0x8],0x3fb
        <+10>:  jg     0x512 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x280
        <+19>:  jne    0x50a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0xa
        <+27>:  jmp    0x529 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0xa
        <+35>:  jmp    0x529 <asm1+60>
        <+37>:  cmp    DWORD PTR [ebp+0x8],0x559
        <+44>:  jne    0x523 <asm1+54>
        <+46>:  mov    eax,DWORD PTR [ebp+0x8]
        <+49>:  sub    eax,0xa
        <+52>:  jmp    0x529 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,0xa
        <+60>:  pop    ebp
        <+61>:  ret 
```
Analizamos el código ensamblador paso a paso usando el argumento `0x2e0` para `[ebp+0x8]`.

`0x2e0` (736 en decimal) es menor que `0x3fb`, por lo que el código continúa a la siguiente comparación.

`0x2e0` (736) es mayor que `0x280`, por lo que salta a la dirección `0x50a`, donde se ejecuta
```bash
mov eax, DWORD PTR [ebp+0x8] ; Carga el argumento en eax, así que eax = 0x2e0 sub eax, 0xa ; Resta 0xa de eax
```
Esto establece `eax` en `0x2e0 - 0xa = 0x2d6`.
## Referencias
[Lenguaje Ensamblador](https://es.wikipedia.org/wiki/Lenguaje_ensamblador)
