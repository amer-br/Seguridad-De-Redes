## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll]
└─$ ls
dolls.jpg
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll]
└─$ unzip dolls.jpg 
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll]
└─$ cd base_images   
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll/base_images]
└─$ ls
2_c.jpg
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MatryoshkaDoll/base_images]
└─$ cd base_images 
                                                                             
┌──(kali㉿kali)-[~/…/forensic/MatryoshkaDoll/base_images/base_images]
└─$ unzip 3_c.jpg 
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
                                                                             
┌──(kali㉿kali)-[~/…/forensic/MatryoshkaDoll/base_images/base_images]
└─$ cd base_images 
                                                                             
┌──(kali㉿kali)-[~/…/MatryoshkaDoll/base_images/base_images/base_images]
└─$ unzip 4_c.jpg 
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
                                                                             
┌──(kali㉿kali)-[~/…/MatryoshkaDoll/base_images/base_images/base_images]
└─$ cat flag.txt 
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b} 
```

