## Objetivo
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm2]
└─$ file test.S 
test.S: ASCII text
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/asm2]
└─$ cat test.S 
asm2:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret  
```

Analizamos el código paso a paso tomando en cuenta los valores pasados `0xb` (11 en decimal) y `0x2e` (46 en decimal) para los argumentos `[ebp+0x8]` y `[ebp+0xc]`, respectivamente.

Se establece un nuevo marco de pila y se reserva espacio:
```bash
push   ebp
mov    ebp, esp
sub    esp, 0x10
```

Se asignan los valores a las variables:
```bash
mov    eax, DWORD PTR [ebp+0xc]    ; eax = 0x2e (valor del segundo argumento)
mov    DWORD PTR [ebp-0x4], eax    ; [ebp-0x4] = 0x2e (inicializa la variable con el segundo argumento)

mov    eax, DWORD PTR [ebp+0x8]    ; eax = 0xb (valor del primer argumento)
mov    DWORD PTR [ebp-0x8], eax    ; [ebp-0x8] = 0xb (inicializa la variable con el primer argumento)
```

Este salto nos lleva al primer `cmp`, que controla un bucle `while`:
```bash
cmp    DWORD PTR [ebp-0x8], 0x63f3  ; Compara [ebp-0x8] con 0x63f3 (25587 en decimal)
jle    0x501 <asm2+20>              ; Si [ebp-0x8] <= 0x63f3, vuelve a la instrucción en 0x501
```

Inicialmente, `[ebp-0x8]` es `0xb` (11), que es menor que `0x63f3`, por lo que entra en el bucle:
```bash
cmp    DWORD PTR [ebp-0x8], 0x63f3  ; Compara [ebp-0x8] con 0x63f3 (25587 en decimal)
jle    0x501 <asm2+20>              ; Si [ebp-0x8] <= 0x63f3, vuelve a la instrucción en 0x501
```

Dentro del bucle, se ejecutan las siguientes instrucciones(La operación `sub DWORD PTR [ebp-0x8], 0xffffff80` es equivalente a sumar `0x80` (128 en decimal) debido al valor negativo en hexadecimal):
```bash
add    DWORD PTR [ebp-0x4], 0x1        ; Incrementa [ebp-0x4] en 1
sub    DWORD PTR [ebp-0x8], 0xffffff80 ; Resta `0xffffff80` de [ebp-0x8]
```

- En cada iteración:
    - `[ebp-0x4]` se incrementa en 1.
    - `[ebp-0x8]` se incrementa en `0x80` (128 en decimal).
- El bucle se repite hasta que `[ebp-0x8]` exceda `0x63f3`.

Cuando `[ebp-0x8]` supera `0x63f3`, el bucle termina, y la función carga el valor de `[ebp-0x4]` en `eax` y retorna ese valor.

El resultado final de la función `asm2(0xb, 0x2e)` es `0xF6` en hexadecimal.
