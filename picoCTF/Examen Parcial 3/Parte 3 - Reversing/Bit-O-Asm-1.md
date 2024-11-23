## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/BOA1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret

```
- **`endbr64`**: Marca para el control de flujo indirecto (usada en sistemas con Control-Flow Enforcement Technology, CET). Específica para seguridad en llamadas indirectas.
    
- **`push rbp`**: Guarda el valor actual del registro `rbp` en la pila, para preservar el marco base anterior de la función llamante.
    
- **`mov rbp, rsp`**: Establece `rbp` como el nuevo marco base de la función actual, apuntando al valor de la pila en este momento.
    
- **`mov DWORD PTR [rbp-0x4], edi`**: Copia el valor del registro `edi` (primer argumento en llamadas de función en el ABI de System V) en la dirección de memoria `[rbp-0x4]`. Se reserva 4 bytes para almacenar este argumento.
    
- **`mov QWORD PTR [rbp-0x10], rsi`**: Copia el valor de `rsi` (segundo argumento en el ABI de System V) en la dirección `[rbp-0x10]`. Se reserva 8 bytes para este argumento.
    
- **`mov eax, 0x30`**: Asigna el valor hexadecimal `0x30` (48 en decimal) al registro `eax`. Esto será el valor de retorno de la función.
    
- **`pop rbp`**: Restaura el marco base anterior desde la pila.
    
- **`ret`**: Devuelve el control al llamador, con el valor de retorno almacenado en `eax`.

```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/BOA1]
└─$ python         
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x30
48
```

picoCTF{48}

