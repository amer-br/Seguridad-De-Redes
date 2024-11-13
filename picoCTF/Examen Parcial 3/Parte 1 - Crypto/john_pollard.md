## Objetivo
Sometimes RSA [certificates](https://jupiter.challenges.picoctf.org/static/c882787a19ed5d627eea50f318d87ac5/cert) are breakable

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/john?pollard]
└─$ openssl x509 -pubkey -in cert -out cert.pub
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/e3/john?pollard]
└─$ openssl rsa -pubin -in cert.pub -text      
Public-Key: (53 bit)
Modulus: 4966306421059967 (0x11a4d45212b17f)
Exponent: 65537 (0x10001)
writing RSA key
-----BEGIN PUBLIC KEY-----
MCIwDQYJKoZIhvcNAQEBBQADEQAwDgIHEaTUUhKxfwIDAQAB
-----END PUBLIC KEY-----
```
Factorizamos el número:  4966306421059967
Dando como resultado: 4966 306421 059967 = 67 867967 × 73 176001
De ahí sacamos que la bandera es: picoCT{73176001,67867967}

