## Objetivo
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/158/challenge.zip)

## Solución
```bash
amer_br_-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amer_br_-picoctf@webshell:~$ cd drop-in/
amer_br_-picoctf@webshell:~/drop-in$ git log --pretty="%an" --no-merges
picoCTF{@sk_th3_1nt3rn_2c6bf174}
picoCTF
```
## Notas adicionales
- `git log`: Muestra el historial de commits.
- `--pretty="%an"`: Muestra solo los nombres de los autores (`%an` es para los nombres de autor).
- `--no-merges`: Excluye los commits de merge para centrarse en los commits individuales.

