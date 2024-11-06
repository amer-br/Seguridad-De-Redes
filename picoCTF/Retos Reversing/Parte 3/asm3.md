## Objetivo
What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

## Solución
Usamos un [emulador del lenguaje ensamblador](https://carlosrafaelgn.com.br/Asm86/) .
Copiamos el código y le borramos la parte donde salen el número de línea en cada línea.
Añadimos a la pila los parámetros que nos índica el reto de manera inversa.
Ejecutamos el programa paso a paso para ver cómo funciona
Al final el valor de EAX es el valor de nuestra flag (omitiendo los ceros intermedios (0x0000669B -> 0x669B)
![[Pasted image 20241105205317.png]]