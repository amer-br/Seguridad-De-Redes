## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

   ### Hints:
   1. How did pictures from the moon landing get sent back to Earth?
   2. What is the CMU mascot?, that might help select a RX option

## Solución

```bash
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162 (from 1)
Receiving objects: 100% (221/221), 1.01 MiB | 942.00 KiB/s, done.
Resolving deltas: 100% (139/139), done.

┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python3 setup.py install                        
running install
/usr/lib/python3/dist-packages/setuptools/_distutils/cmd.py:66: SetuptoolsDeprecationWarning: setup.py install is deprecated.


┌──(kali㉿kali)-[~/picoCTFretos/forensic/m00nwalk]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [###########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/m00nwalk]
└─$ ls
message.wav  result.png

```
![[Pasted image 20241005185414.png]]
## Notas adicionales

**Scotty** -Universidad Carnegie Mellon/Mascota
## Referencias
[Repositorio sstv](https://github.com/colaclanth/sstv)

