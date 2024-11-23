## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/BOA3]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret

```
1. **Configuración del marco de la pila**:
    
    - `push rbp` y `mov rbp, rsp` establecen el marco base de la función.
    - Esto permite gestionar variables locales y almacenar argumentos de manera organizada.
2. **Almacenamiento de argumentos**:
    
    - `edi` (primer argumento) se guarda en `[rbp-0x14]`.
    - `rsi` (segundo argumento) se guarda en `[rbp-0x20]`.
3. **Asignación de valores constantes**:
    
    - `mov DWORD PTR [rbp-0xc], 0x9fe1a`: Se asigna el valor `0x9fe1a` (654106 en decimal) a `[rbp-0xc]`.
    - `mov DWORD PTR [rbp-0x8], 0x4`: Se asigna el valor `0x4` (4 en decimal) a `[rbp-0x8]`.
4. **Cálculo del resultado**:
    
    - `mov eax, DWORD PTR [rbp-0xc]`: Carga el valor `0x9fe1a` en el registro `eax`.
    - `imul eax, DWORD PTR [rbp-0x8]`: Multiplica `eax` (654106) por el valor almacenado en `[rbp-0x8]` (4), resultando en `2616424`.
    - `add eax, 0x1f5`: Suma el valor `0x1f5` (501 en decimal) al resultado anterior (`2616424`), dando `2616925`.
5. **Almacenamiento del resultado**:
    
    - `mov DWORD PTR [rbp-0x4], eax`: Guarda el valor final  en `[rbp-0x4]`.
6. **Retorno del resultado**:
    
    - `mov eax, DWORD PTR [rbp-0x4]`: Carga el valor almacenado en `[rbp-0x4]`  en `eax`.
    - `pop rbp` y `ret`: Restaura el marco base anterior y devuelve el control al llamador, con `eax` como el valor de retorno.


La función devuelve el valor calculado en `eax`, que es:

Resultado = (0x9fe1a * 0x4) + 0x1f5

Resultado = (654874 * 4) + 501 = 2619997

Dando como flag: picoCTF{2619997}
