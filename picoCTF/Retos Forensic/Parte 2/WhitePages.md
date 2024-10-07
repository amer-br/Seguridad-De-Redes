## Objetivo
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/forensic/WhitePages]
└─$ ls
whitepages.txt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/WhitePages]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/WhitePages]
└─$ xxd whitepages.txt | head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........
```
Reemplazar los distintos espacios por 0 y 1.

![[Pasted image 20241007104856.png]]

Lo traducimos en cyberchef.

![[Pasted image 20241007105025.png]]
## Notas adicionales
**328083** - Representa un espacio
## Referencias
[Unicode](https://en.wikipedia.org/wiki/Unicode)
[UTF-8](https://es.wikipedia.org/wiki/UTF-8)
