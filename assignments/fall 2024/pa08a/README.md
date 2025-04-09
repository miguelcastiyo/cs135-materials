```
REVISION HISTORY:
2023-11-09: Original
```

# pa08a

![Snakes and Ladders game board](https://as2.ftcdn.net/v2/jpg/04/71/35/61/1000_F_471356144_rQ4ELeb0p59MXaf8Mrf8df9XMz5j6sCd.jpg)

## Snakes and Ladders

Have you ever heard the expression, "back to square one"? It originated in the game of snakes and ladders.

Snakes and Ladders is a board game for two or more players regarded today as a worldwide classic. The game originated in ancient India as Moksha Patam. It is played on a game board with numbered, gridded squares. A number of "ladders" and "snakes" are pictured on the board, each connecting two specific board squares. The object of the game is to navigate one's game piece, according to die rolls, from the start (bottom square) to the finish (top square), helped by climbing ladders but hindered by falling down snakes.

The game is a simple race based on sheer luck, and it is popular with young children. The historic version had its roots in morality lessons, where a player's progression up the board represented a life journey complicated by virtues (ladders) and vices (snakes).

## Game Board and Play Overview

Each player starts with a token on the starting square (the "1" grid square in the bottom left corner). Players take turns rolling a single die to move their token by the number of squares indicated by the die roll. Tokens follow a fixed route marked on the game board, which follows a boustrophedon (ox-plow) track from the bottom to the top of the playing area, passing once through every square. If, on completion of a move, a player's token lands on the lower-numbered end of a "ladder", the player moves the token up to the ladder's higher-numbered square. If the player lands on the higher-numbered square of a "snake", the token must be moved down to the snake's lower-numbered square. The game concludes immediately when any player's token reaches the last square of the track.

## Game Rules

- The game is played on a 10 by 10 grid.
- The squares of the grid are numbered 1 to 100.
- Each player has a token which is placed on the square numbered 1 at the beginning of the game.
- Players take turns rolling a die which provides a random number between 1 and 6.
    - After rolling, the player advances their token the number of squares shown on the die. If a player rolls a number that would advance their token beyond the square numbered 100, the token does not move, and the player must wait for their next turn to roll again.
    - After advancing, if the token is on a square containing the bottom of a ladder, the token must be moved to the square containing the top of the ladder. Similarly, if the token is on a square containing the mouth of a snake, the token must be moved to the square containing the tail of the snake.
- No square contains more than one endpoint of any snake or ladder. (i.e., no square contains more than one bottom rung of a ladder or head of a snake).
- The square numbered 100 does not contain the mouth of a snake or the bottom of a ladder.
- The first player whose token reaches the square numbered 100 wins the game. No further die rolls are processed after the game concludes.

## Problem Description

Given the configuration of the snakes and ladders on a game board and a sequence of die rolls, determine the positions of all the tokens on the game board. The sequence of die rolls need not be complete (i.e., it need not lead to any player winning). The sequence of die rolls may continue after a player has won; however, those rolls should be ignored.

## Input Specification

The first line is the number of test cases to follow. The test cases follow, one after another. For each test case, the first line contains three positive integers: the number of players, A, the number of snakes or ladders, B, and the number of die rolls, C. For the next B lines, each line contains two integers:
- The first integer indicates the square containing the bottom of a ladder or the mouth of a snake.
- The second integer indicates the square containing the top of a ladder or the tail of a snake.
- Ensure that for ladders, the first integer is less than the second, and for snakes, the first integer is greater than the second. 
- There will be no more than 1'000 players and no more than 1'000 die rolls. 
- Each of the next B lines contains two integers specifying a snake or ladder.
- The following C lines each contain one integer, indicating the number rolled on the die.

## Output Specification

For each player, output a single line containing a string of the form "Player N is at position P.", where N is replaced with the number of the player and P is replaced with the final position of the player on the board.

## Sample Input

```
1
3 1 3
4 14
3
4
5
```

### Explanation

1. The first line 1 indicates that there is one test case to follow.
2. The second line 3 1 3 indicates three parameters for this test case:
    - 3 is the number of players.
    - 1 is the number of snakes or ladders on the board.
    - 3 is the number of die rolls that will be processed.
3. The third line `4 14` describes the positions of the snakes or ladders:
    - The ladder starts at square 4 and ends at square 14. Since the starting number is less than the ending number, it's a ladder.
4. The next three lines represent the die rolls for the players:
    - 3 is the first die roll.
    - 4 is the second die roll.
    - 5 is the third die roll.

## Sample Output

```
Player 1 is at position 14.
Player 2 is at position 5.
Player 3 is at position 6.
```

### Step by step game progression

1. First Roll (3): Player 1 rolls a 3, moving from square 1 to square 4. Since square 4 is the bottom of a ladder, Player 1 moves up to square 14. Thus, Player 1 is now at position 14.

2. Second Roll (4): Player 2 rolls a 4, moving from square 1 to square 5. There is no ladder or snake at square 5, so Player 2 stays at position 5.

3. Third Roll (5): Player 3 rolls a 5, moving from square 1 to square 6. Like Player 2, there is no ladder or snake at square 6, so Player 3 stays at position 6.

**Result:**

- Player 1 ends at square 14 because they encountered a ladder on their first roll.
- Player 2 is at square 5, which was the result of their first roll.
- Player 3 is at square 6, also the result of their first roll.

Since each player only rolled once in this sequence, and there were no further rolls or ladders/snakes affecting their positions after their initial move, the final positions correspond directly to the outcomes of their individual rolls.

## Program-Specific Requirements

- Ensure that your program adheres to the concepts and features introduced in the chapters covered by the course textbook. Usage of any C++ features or libraries not yet introduced in the assigned chapters (1-8) is not permitted and *may result in a zero score for the assignment*.
- Incorporate array(s) into your algorithm.
- Prototype, document, define, and use functions to modularize your solution. Functions should do one specific task.
- Target no more than 35 statements (excluding blank lines and comment lines) in function `main()`. (Keep it short and simple.)

## The Judge

- Test inputs and expected outputs can be copied to your project directory:
  ```bash
  $ cp /home/shared/cs135/kmess/pa08a/*.txt ~/cs135/pa08a/
  ```
- Run the Judge
  ```bash
  $ judge —p pa08a —i pa08a—input0.txt —o pa08a—output0.txt —v
  ```
- If your program did not receive an "Accepted" verdict, review the output and the verdict message to identify and fix the issue in your code.
- Make necessary adjustments to your program, rerun the script, and repeat the process until you receive an "Accepted" verdict.
- There may be other sets of test inputs and expected outputs. Be sure to check your program with them all.

## Submission

- Name your source code file `pa08a.cpp`.
- Use the `lint` utility (either from within Geany or from the command line) to analyze your source code and resolve as many diagnostic issue as possible. (If uncertain about what a diagnostic message means, please ask in our Discord channel so an answer is available to all.)
- Use the following command to submit your work for grading:

```bash
$ turnin —c cs135-kmess —p pa08a —v pa08a.cpp
```

## References

https://en.wikipedia.org/wiki/Snakes_and_ladders

<!--EOF-->

