## Objetivo
Someone might have hidden the password in the trace file. Find the key to unlock [this file](https://artifacts.picoctf.net/c/493/flag.zip). [This tracefile](https://artifacts.picoctf.net/c/493/dump.pcap) might be good to analyze.

## Solución
Comiamos la data del paquete 48 y lo ponemos en cyberchef, con esto obtenemos la contraseña del archivo zip
![[Pasted image 20241026094144.png]]
Descomprimimos el archivo zip para obtener la bandera:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/crypto/FindAndOpen]
└─$ unzip flag.zip                                       
Archive:  flag.zip
[flag.zip] flag password: 
 extracting: flag                    
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/FindAndOpen]
└─$ ls
dump.pcap  flag  flag.zip
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/FindAndOpen]
└─$ file flag             
flag: ASCII text
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/FindAndOpen]
└─$ cat flag    
picoCTF{R34DING_LOKd_fil56_succ3ss_419835ef}
```

## Notas adicionales
## Referencias
