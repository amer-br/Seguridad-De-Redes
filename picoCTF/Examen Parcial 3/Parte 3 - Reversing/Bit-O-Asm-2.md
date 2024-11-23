## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Solución

```bash
──(kali㉿kali)-[~/picoCTFretos/e3/BOA2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
```
- **Preparación del marco de la pila**:
    
    - `push rbp` y `mov rbp, rsp` configuran el marco base de la función, permitiendo que las variables locales se asignen en la pila.
- **Almacenamiento de los argumentos**:
    
    - **`edi`**: Este es el primer argumento de la función. Se guarda en la dirección `[rbp-0x14]`.
    - **`rsi`**: Este es el segundo argumento de la función. Se guarda en la dirección `[rbp-0x20]`. Esto es una convención común en llamadas de función en sistemas que usan el **ABI de System V**.
- **Asignación de una constante**:
    
    - La línea `mov DWORD PTR [rbp-0x4], 0x9fe1a` almacena el valor constante `0x9fe1a` (654 en decimal) en una variable local ubicada en `[rbp-0x4]`.
- **Copia de la constante al registro de retorno**:
    
    - `mov eax, DWORD PTR [rbp-0x4]` carga el valor de `[rbp-0x4]` en el registro `eax`, que es el registro donde se almacena el valor de retorno de las funciones.
- **Restauración del marco de pila y retorno**:
    
    - `pop rbp` restaura el marco base anterior.
    - `ret` devuelve el control al llamador, con el valor en `eax` como el resultado de la función.

Al convertir el número 0x9fe1a en decimal nos da el numéro 654874, dando como flag:
picoCTF{654874}
