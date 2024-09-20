## Objetivo
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.

## Solución
```bash
amer_br_-picoctf@webshell:~$ nc saturn.picoctf.net 62931
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
```
Usando cyberchef descodifiqué cada letra (ej. chr(0x62)) para encontrar el resto de la bandera. Dando como resultado picoCTF{gl17ch_m3_n07_bda68f75}
