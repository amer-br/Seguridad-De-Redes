## Objetivo
Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`. The flag is the four bytes as they are stored in memory. If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`. Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).

## Solución
```bash
(gdb) break main
Breakpoint 1 at 0x40110e
(gdb) start
Temporary breakpoint 2 at 0x40110e
Starting program: /home/kali/picoCTFretos/e3/GDB3/debugger0_c 

(gdb) disas main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:    pop    %rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) break *0x000000000040111f
Breakpoint 3 at 0x40111f
(gdb) c
Continuing.

Breakpoint 3, 0x000000000040111f in main ()
(gdb) x/4xb $rbp-4
0x7fffffffdfcc: 0x6b    0xc9    0x62    0x22
```
## Notas adicionales
## Referencias
