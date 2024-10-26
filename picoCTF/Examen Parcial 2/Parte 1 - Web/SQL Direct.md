## Objetivo
Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 56920 -U postgres pico` Password is `postgres`

## Solución
```bash
└─$ psql -h saturn.picoctf.net -p 56920 -U postgres pico 
Password for user postgres: 
psql (16.3 (Debian 16.3-1+b1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \l
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# SELECT * FROM FLAGS
pico-# SELECT * FROM flags;
ERROR:  syntax error at or near "SELECT"
LINE 2: SELECT * FROM flags;
        ^
pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

```
## Notas adicionales
**SQL Direct** es una actividad asincrónica que ejecuta una sentencia SQL que usted proporciona. Con esta actividad, puede crear una sentencia SQL de forma dinámica utilizando otras actividades y, a continuación, pasar la sentencia SQL a la entrada de esta actividad.