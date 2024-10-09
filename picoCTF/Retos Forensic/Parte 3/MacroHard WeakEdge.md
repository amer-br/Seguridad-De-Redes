## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics is fun.pptm)

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MacroHard]
└─$ unzip Forensics\ is\ fun.pptm 
Archive:  Forensics is fun.pptm
  inflating: [Content_Types].xml     
  inflating: _rels/.rels             
  inflating: ppt/presentation.xml    
  inflating: ppt/slides/_rels/slide46.xml.rels
  ...
  inflating: docProps/app.xml        
  inflating: ppt/slideMasters/hidden  
                                      
┌──(kali㉿kali)-[~/picoCTFretos/forensic/MacroHard]
└─$ cd ppt/slideMasters 
                                                                             
┌──(kali㉿kali)-[~/…/forensic/MacroHard/ppt/slideMasters]
└─$ ls
hidden  _rels  slideMaster1.xml
                                                                             
┌──(kali㉿kali)-[~/…/forensic/MacroHard/ppt/slideMasters]
└─$ file hidden 
hidden: ASCII text, with no line terminators
                                                                             
┌──(kali㉿kali)-[~/…/forensic/MacroHard/ppt/slideMasters]
└─$ cat hidden         
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                             
┌──(kali㉿kali)-[~/…/forensic/MacroHard/ppt/slideMasters]
└─$ cat hidden |tr -d ' '|base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input

```
