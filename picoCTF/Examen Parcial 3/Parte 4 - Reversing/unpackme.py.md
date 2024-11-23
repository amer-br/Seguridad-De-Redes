## Objetivo
Can you get the flag? Reverse engineer this [Python program](https://artifacts.picoctf.net/c/49/unpackme.flag.py).

## Solución

Cambiamos el código que nos dan(sólo cambiamos el último exc por un print para que nos muestre la bandera):
```bash
import base64

from cryptography.fernet import Fernet

payload = b'gAAAAABkzWGSzE6VQNTzvRXOXekQeW4CY6NiRkzeImo9LuYBHAYw_hagTJLJL0c-kmNsjY33IUbU2IWlqxA3Fpp9S7RxNkiwMDZgLmRlI9-lGAEW-_i72RSDvylNR3QkpJW2JxubjLUC5VwoVgH62wxDuYu1rRD5KadwTADdABqsx2MkY6fKNTMCYY09Se6yjtRBftfTJUL-LKz2bwgXNd6O-WpbfXEMvCv3gNQ7sW4pgUnb-gDVZvrLNrug_1YFaIe3yKr0Awo0HIN3XMdZYpSE1c9P4G0sMQ=='

key_str = 'correctstaplecorrectstaplecorrec'

key_base64 = base64.b64encode(key_str.encode())

f = Fernet(key_base64)

plain = f.decrypt(payload)

print(plain.decode())
```

Al ejecutarlo nos da la bandera:
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/unpackme.py]
└─$ python unpackme.flag.py 

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_cd82f94c}')
else:
  print('That password is incorrect.')

```
## Notas adicionales
## Referencias
