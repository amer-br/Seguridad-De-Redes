## Objetivo

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)
## Solución
```
┌──(kali㉿kali)-[~/picoCTFretos/crypto/pindyourpsandqs]
└─$ ls
values
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/crypto/pindyourpsandqs]
└─$ cat values        
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537             

Factorizamos n para obtener los valores de p y q.

┌──(kali㉿kali)-[~/picoCTFretos/crypto/pindyourpsandqs]
└─$ python3                                                 
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> e=65537
>>> p=2159947535959146091116171018558446546179
>>> q=658558036833541874645521278345168572231473
>>> n=p*q
>>> n
1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> tn = (p-1) * (q-1)
>>> tn
1422450808944701344261903748621562998783582944057933890341955406374353056752914016
>>> d=pow(e,-1,tn)
>>> d
975120122884150896343356420256053234758228648361853546720066993334766006694511009
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639555294957886055592061
>>> bytes.fromhex(hex(m)[2:]).decode()
'picoCTF{sma11_N_n0_g0od_00264570}'
```
