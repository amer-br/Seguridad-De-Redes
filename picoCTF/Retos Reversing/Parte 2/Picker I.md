## Objetivo
This service can provide you with a random number, but can it do anything else? Connect to the program with netcat: `$ nc saturn.picoctf.net 63240` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/515/picker-I.py).

## Solución
Vemos el código y nos damos cuenta que tenemos que ingresar la palabra win para que nos muestre la bandera en hexadecimal.
```bash
──(kali㉿kali)-[~/picoCTFretos/Reversing/picker1]
└─$ nc saturn.picoctf.net 63240                            
Try entering "getRandomNumber" without the double quotes...
==> win
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x65 0x34 0x62 0x35 0x64 0x35 0x62 0x7d 
Try entering "getRandomNumber" without the double quotes...
==>  
```
Después descodificamos la bandera en cyberchef y así obtenemos la bandera picoCTF{4_d14m0nd_1n_7h3_r0ugh_ce4b5d5b}:
![[Pasted image 20241031222750.png]]

