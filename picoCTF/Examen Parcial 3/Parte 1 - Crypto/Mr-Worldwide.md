## Objetivo
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/e3/mrWorldwide]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}
```
Buscamos la ubicación de cada coordenada:
35.028309, 135.753082  - Kioto, Japón
46.469391, 30.740883 - Odesa, Ucrania
39.758949, -84.191605 - Dayton, Ohio, EUA
41.015137, 28.979530 - Istambul
24.466667, 54.366669 - Abu Dabi - Emiratos Árabes Unidos
3.140853, 101.693207 - Kuala Lumpur, Territorio Federal de Kuala Lumpur, Malasia
_
9.005401, 38.763611 - Adís Abeba, Etiopía
-3.989038, -79.203560 - Loja, Ecuador
52.377956, 4.897070 - Ámsterdam, Países Bajos
41.085651, -73.858467 - Sleepy Hollow, Nueva York, EE. UU.
57.790001, -152.407227 - Kodiak, Alaska, EE. UU
31.205753, 29.924526 -  Alejandría, Egipto

Tomamos la inicial de cada lugar dando la bandera: picoCTF{KODIAK_ALASKA}

