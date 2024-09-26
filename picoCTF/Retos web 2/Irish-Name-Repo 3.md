## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

## Solución
En interfaz:
Probamos cualquier contraseña para ver cuál es el resultado de la consulta
![[Pasted image 20240925202710.png]]
Vemos que la contraseña está encriptada con un ROT13, así que buscamos el equivalente para que la sentencia SQL termine en or 1=1 para tener acceso.
![[Pasted image 20240925203117.png]]

Probamos con la inyección **' be 1 = 1;** y con eso ya tuvimos acceso.
![[Pasted image 20240925203200.png]]


