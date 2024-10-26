## Objetivo
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).

## Solución
La segunda parte de la bandera está directamente en el documento que descargamos.
Para obtener la primera parte hacemos lo siguiente:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/secretOfThePolyglot]
└─$ cp flag2of2-final.pdf flag.png                              
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/secretOfThePolyglot]
└─$ open flag.png&  
```
![[Pasted image 20241026141213.png]]
