## Objetivo
All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: [dds2-alpine.flag.img.gz](https://mercury.picoctf.net/static/9061ae8456a4ff51098c5183d910a080/dds2-alpine.flag.img.gz)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdisksleuthII]
└─$ fls -r  dds2-alpine.flag.img -o 2048 | grep down
++ d/d 2177:    if-down.d
++ d/d 2178:    if-post-down.d
++ d/d 2180:    if-pre-down.d
++ d/d 2204:    shutdown
+ r/r 18291:    down-at-the-bottom.txt
+ l/l 18311:    ifdown
+ r/r 18344:    openrc-shutdown
+++++ r/r 12472:        down.sh
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/diskdisksleuthII]
└─$ icat ./dds2-alpine.flag.img -o 2048 18291
   _     _     _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( p ) ( i ) ( c ) ( o ) ( C ) ( T ) ( F ) ( { ) ( f ) ( 0 ) ( r ) ( 3 ) ( n )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 
   _     _     _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( s ) ( 1 ) ( c ) ( 4 ) ( t ) ( 0 ) ( r ) ( _ ) ( n ) ( 0 ) ( v ) ( 1 ) ( c )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 
   _     _     _     _     _     _     _     _     _     _     _  
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \ 
 ( 3 ) ( _ ) ( 8 ) ( 2 ) ( 4 ) ( 8 ) ( 9 ) ( d ) ( b ) ( f ) ( } )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/ 

```

## Notas adicionales
## Referencias
