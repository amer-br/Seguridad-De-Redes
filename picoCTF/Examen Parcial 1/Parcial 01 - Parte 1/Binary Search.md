## Objetivo
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/5/challenge.zip)

Additional details will be available after launching your challenge instance.
## Solución
```bash
amer_br_-picoctf@webshell:~$ ssh -p 57841 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 750
Lower! Try again.
Enter your guess: 600
Higher! Try again.
Enter your guess: 700
Lower! Try again.
Enter your guess: 650
Higher! Try again.
Enter your guess: 675
Lower! Try again.
Enter your guess: 660
Lower! Try again.
Enter your guess: 655
Congratulations! You guessed the correct number: 655
Here's your flag: picoCTF{g00d_gu355_3af33d18}
Connection to atlas.picoctf.net closed.
```

