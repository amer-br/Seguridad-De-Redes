## Objetivo
Here's a program that plays rock, paper, scissors against you. I hear something good happens if you win 5 times in a row. The program's source code with the flag redacted can be downloaded [here](https://artifacts.picoctf.net/c/146/game-redacted.c). Connect to the program with netcat: `$ nc saturn.picoctf.net 56279`

## Solución
```bash
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1
1


Please make your selection (rock/paper/scissors):
rockpaperscissors
rockpaperscissors
You played: rockpaperscissors
The computer played: paper
You win! Play again?
Type '1' to play a game
Type '2' to exit the program
1
1


Please make your selection (rock/paper/scissors):
rockpaperscissors
rockpaperscissors
You played: rockpaperscissors
The computer played: paper
You win! Play again?
Congrats, here's the flag!
picoCTF{50M3_3X7R3M3_1UCK_B69E01B8}
Type '1' to play a game
Type '2' to exit the program

```
## Notas adicionales
## Referencias
