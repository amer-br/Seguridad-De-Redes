## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/crypto/pixelated]
└─$ sudo apt install imagemagick
imagemagick is already the newest version (8:6.9.13.12+dfsg1-1).
imagemagick set to manually installed.
The following packages were automatically installed and are no longer required:
  ibverbs-providers         libgfxdr0          python3-lib2to3
  libboost-iostreams1.83.0  libglusterfs0      python3.11
  libboost-thread1.83.0     libibverbs1        python3.11-dev
  libcephfs2                libpython3.11-dev  python3.11-minimal
  libgfapi0                 librados2          samba-vfs-modules
  libgfrpc0                 librdmacm1t64
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1112
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite bandera.png 
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/pixelated]
└─$ ls
bandera.png  scrambled1.png  scrambled2.png

```
![[Pasted image 20241023110700.png]]
## Notas adicionales
## Referencias
