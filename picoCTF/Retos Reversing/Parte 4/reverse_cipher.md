## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.

## Solución

Usamos ghidra para abrir el archivo rev:
![[Pasted image 20241106000421.png]]

Luego a partir del código podemos hacer un script de python para desencriptar la bandera:
![[Pasted image 20241106000523.png]]

Dando como resultado: r3v3rs37ee84d27
## Notas adicionales
## Referencias
