## Objetivo

I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check... Connect to the program on our server: `nc saturn.picoctf.net 54455` Download the program: [chal.py](https://artifacts.picoctf.net/c/295/chal.py)
## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ python /m venv venv
python: can't open file '/m': [Errno 2] No such file or directory
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ python -m venv venv
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ source venv/bin/activate  
                                                                             
┌──(venv)─(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ pip install primefac
Collecting primefac
  Downloading primefac-2.0.12-py3-none-any.whl.metadata (13 kB)
Downloading primefac-2.0.12-py3-none-any.whl (54 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.8/54.8 kB 326.1 kB/s eta 0:00:00
Installing collected packages: primefac
Successfully installed primefac-2.0.12
                                                                             
┌──(venv)─(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ pip install sympy
Collecting sympy
  Downloading sympy-1.13.3-py3-none-any.whl.metadata (12 kB)
Collecting mpmath<1.4,>=1.1.0 (from sympy)
  Downloading mpmath-1.3.0-py3-none-any.whl.metadata (8.6 kB)
Downloading sympy-1.13.3-py3-none-any.whl (6.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.2/6.2 MB 797.7 kB/s eta 0:00:00
Downloading mpmath-1.3.0-py3-none-any.whl (536 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 1.2 MB/s eta 0:00:00
Installing collected packages: mpmath, sympy
Successfully installed mpmath-1.3.0 sympy-1.13.3
                                                                             
┌──(venv)─(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ pip install pwntools
```

```bash
──(venv)─(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ nano solve.py 

from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes
#function to generate all the sub lists
def sub_lists (l):
    #initializing empty list
    comb = []
    #Iterating till length of list
    for i in range(1,len(l)+1):
        #Generating sub list
        comb += [list(j) for j in combinations(l, i)]
    #Returning list
    return comb
def divisors(phi):
   print("Give me the divisors of ", phi-1)
   #this is dangerous, but I'm trusting me
   return(eval(input()))
#connect to the server
r = remote('saturn.picoctf.net', 61245)
#get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
#get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
#since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
   #multiply them together to get p-1
   for k in l:
      product = product * k
   #if the right length and adding 1 yields a prime, then maybe
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
#try all possible prime pairs
for p in primelist:
   for q in primelist:
      n=p*q
      #decode with this possible n
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
         #see if it corresponds to text and if so, try it
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue

```
Ejecutamos el código:
```bash
┌──(venv)─(kali㉿kali)-[~/picoCTFretos/e3/sra]
└─$ python solve.py 
[▄] Opening connection to saturn.picoctf.net on port 61245: Trying 13.59.203.[+] Opening connection to saturn.picoctf.net on port 61245: Done
/home/kali/picoCTFretos/e3/sra/solve.py:22: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/picoCTFretos/e3/sra/solve.py:25: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 31387075298090089371852702340079056427629472577998148195163520260289246453283
d= 6128371426307679242758904361030828437862282110425600549746716277733935700673
/home/kali/picoCTFretos/e3/sra/solve.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  401635078165926374532690315108877403332180382670962583228750544693848944015006400
...
[2, 2, 2, 2, 2, 2, 3, 3, 3, 3, 5, 5, 23, 23, 719, 1063, 7907, 275447888545261[2, 2, 2, 2, 2, 2, 3, 3, 3, 3, 5, 5, 23, 23, 719, 1063, 7907, 275447888545261, 28603770900817279, 123036602615968967177430645729571]  
{211073873200986369622617118116559120861, 277387145371841769011085763013942012641, 263645362414908100523283515979296061257, 183119066771425092919185352958692406431}
pzDwgr0TdrprUC7k
/home/kali/picoCTFretos/e3/sra/solve.py:57: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> pzDwgr0TdrprUC7k\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_2b7ad1ae}\r\n'
pzDwgr0TdrprUC7k
[*] Closed connection to saturn.picoctf.net port 61245
```