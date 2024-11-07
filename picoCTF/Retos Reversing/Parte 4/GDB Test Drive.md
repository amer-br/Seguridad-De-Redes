## Objetivo
Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/85/gdbme). Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

## Solución
Descargamos el archivo y seguimos las instrucciones que indica el reto:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/GDBTestDrive]
└─$ chmod +x gdbme 
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/GDBTestDrive]
└─$ gdb gdbme
GNU gdb (Debian 15.1-1) 15.1
Copyright (C) 2024 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
```

![[Pasted image 20241105213946.png]]
picoCTF{d3bugg3r_dr1v3_197c378a}
## Notas adicionales
## Referencias
