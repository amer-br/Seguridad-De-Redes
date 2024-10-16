## Objetivo
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdiskseluth]
└─$ ls -la
total 29080
drwxrwxr-x  2 kali kali     4096 Oct 14 12:30 .
drwxrwxr-x 19 kali kali     4096 Oct 14 12:29 ..
-rw-rw-r--  1 kali kali 29768910 Mar 15  2021 dds1-alpine.flag.img.gz
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdiskseluth]
└─$ gzip -d dds1-alpine.flag.img.gz 
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdiskseluth]
└─$ ls    
dds1-alpine.flag.img
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdiskseluth]
└─$ srch_strings dds1-alpine.flag.img|grep picoCTF
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}

```

