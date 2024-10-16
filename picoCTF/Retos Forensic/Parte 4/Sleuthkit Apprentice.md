## Objetivo

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)
## Solución
```bash
+ r/r 2363:     .ash_history
+ d/d 3981:     my_folder
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/SleuthkinApprendice]
└─$ fls -o 360448 disk.flag.img -r 1995           
r/r 2363:       .ash_history
d/d 3981:       my_folder
+ r/r * 2082(realloc):  flag.txt
+ r/r 2371:     flag.uni.txt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/SleuthkinApprendice]
└─$ fls -o 360448 disk.flag.img -r 2363
Error extracting file from image (ext2fs_dir_open_meta: Error reading directory contents: 2363
)
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/SleuthkinApprendice]
└─$ icat -o 360448 disk.flag.img -r 2363
apk add nano
mkdir my_folder
cd my_folder/
nano flag.txt
ls -al
iconv -f ascii -t utf16 > flag.uni.txt
l
ls -al
iconv -f ascii -t utf16 flag.txt > flag.uni.txt
ls -al
shred
shred -zu flag.txt 
ls -al
halt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/SleuthkinApprendice]
└─$ icat -o 360448 disk.flag.img -r 2371
picoCTF{by73_5urf3r_2f22df38}

```
## Notas adicionales
## Referencias
