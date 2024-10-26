## Objetivo
How about some hide and seek heh? Download this [file](https://artifacts.picoctf.net/c/371/trace.pcap) and find the flag.

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/pcapPoisoning]
└─$ 
[1]  + done       open trace.pcap
┌──(kali㉿kali)-[~/picoCTFretos/forensic/pcapPoisoning]
└─$ file trace.pcap 
trace.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Raw IPv4, capture length 65535)
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/pcapPoisoning]
└─$ strings trace.pcap | grep picoCTF
picoCTF{P64P_4N4L7S1S_SU55355FUL_fc4e803f}3~

```
## Notas adicionales
## Referencias
