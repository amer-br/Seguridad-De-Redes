## Objetivo
[keygenme-trial.py](https://mercury.picoctf.net/static/fb75b48f9214cf992a2199b5785564e7/keygenme-trial.py)

## Solución
En el código esta la primera parte de la bandera:
```bash
#============================================================================#
#============================ARCANE CALCULATOR===============================#
#============================================================================#

import hashlib
from cryptography.fernet import Fernet
import base64



# GLOBALS --v
arcane_loop_trial = True
jump_into_full = False
full_version_code = ""

username_trial = "FREEMAN"
bUsername_trial = b"FREEMAN"

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"
key_part_dynamic1_trial = "xxxxxxxx"
key_part_static2_trial = "}"
key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial

star_db_trial = {
```

En base al código obtenemos la segunda parte:
```bash
┌──(kali㉿kali)-[~/picoCTFretos/e3/keygenme]
└─$ python3
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import hashlib
>>> hashlib.sha256(b"FREEMAN").hexdigest()
'09820d032d73c31bd8f4a0532062a239d828a4da0951aeb66da928e843597e35'
>>> t=hashlib.sha256(b"FREEMAN").hexdigest()
>>> key= t[4]+t[5]+t[3]+t[6]+t[2]+t[7]+t[1]+t[8]
>>> key
'0d208392'

