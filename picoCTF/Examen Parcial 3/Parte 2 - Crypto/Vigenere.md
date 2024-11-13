## Objetivo
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/vigenere]
└─$ cat cipher.txt                              
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}
```

Usando [Vigenere Solver](https://www.dcode.fr/vigenere-cipher) para desencriptar con la palabra CYLAB como key nos da la bandera: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}
![[Pasted image 20241113000445.png]]
## Notas adicionales
El **cifrado de Vigenère** es un cifrado basado en diferentes series de caracteres o letras del [cifrado César](https://es.wikipedia.org/wiki/Cifrado_C%C3%A9sar "Cifrado César") formando estos caracteres una tabla, llamada **tabla de Vigenère**, que se usa como clave. El cifrado de Vigenère es un [cifrado por sustitución](https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n "Cifrado por sustitución") simple polialfabético.
## Referencias
[Cifrado de Vigenere](https://es.wikipedia.org/wiki/Cifrado_de_Vigen%C3%A8re)
