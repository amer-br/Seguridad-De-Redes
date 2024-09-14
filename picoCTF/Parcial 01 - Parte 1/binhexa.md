## Objetivo
How well can you perfom basic binary operations?

Additional details will be available after launching your challenge instance.

## Solución
```bash
amer_br_-picoctf@webshell:~$ nc titan.picoctf.net 65202

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11111100
Binary Number 2: 01000010


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100111110
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 111111000
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01000000
Correct!

Question 4/6:
Operation 4: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100000011111000
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 1111110
Incorrect. Try again
Enter the binary result: 100001
Correct!

Question 6/6:
Operation 6: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111110
Correct!

Enter the results of the last operation in hexadecimal: FE

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d6f8047e}
```
## Referencias
[Calculadora Binaria](https://www.rapidtables.com/calc/math/binary-calculator.html)
[Binario a Hexadecimal ](https://masterplc.com/calculadora/convertir-binario-a-hexadecimal/)
