## Objetivo

Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 62950` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/526/picker-III.py).
## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/picker3]
└─$ nc saturn.picoctf.net 62950
==> []\';                 
Did not understand "[]\';" Have you tried "help"?
==> ?    

This program fixes vulnerabilities in its predecessor by limiting what
functions can be called to a table of predefined functions. This still puts
the user in charge, but prevents them from calling undesirable subroutines.

* Enter 'quit' to quit the program.
* Enter 'help' for this text.
* Enter 'reset' to reset the table.
* Enter '1' to execute the first function in the table.
* Enter '2' to execute the second function in the table.
* Enter '3' to execute the third function in the table.
* Enter '4' to execute the fourth function in the table.

Here's the current table:
  
1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 1
1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 2
Please enter variable name to read: hola
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/Reversing/picker3]
└─$ nc saturn.picoctf.net 62950
==> 3
Please enter variable name to write: getRandomNumber
Please enter new value of variable: win
==> 2
Please enter variable name to read: getRandomNumber
<function win at 0x7a0885de6dc0>
==> 4 
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x32 0x32 0x36 0x64 0x64 0x32 0x38 0x35 0x7d 

```