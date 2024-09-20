## Objetivo
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...

## Solución
Al conectarme al puerto salen puros números
```bash
amer_br_-picoctf@webshell:~$ nc mercury.picoctf.net 49039
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
51 
100 
56 
52 
101 
100 
99 
56 
125 
10 
```
Al buscar su equivalente en el código ASCII da como resultado la bandera picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
## Notas adicionales
## Referencias
[Código AsCII](https://elcodigoascii.com.ar/)