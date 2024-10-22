## Objetivo
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.
## Solución
Ejecutando este código de python
```bash
from gmpy2 import *

gmpy2.get_context().precision = 2048

n = 293319224997949857827359760455911649366830593805589503865601601057403432>
e= 3
c = 220531641393113403107460374692824779903015522125251987265007301078204917>

for t in range(10000):
        m, tr = iroot(t*n + c, e)
        if tr:
                print('Encontre t : ' + str(t))
                print('Flag       : ' + str(bytes.fromhex(hex(m)[2:]).decode>

```

![[Pasted image 20241021114654.png]]

