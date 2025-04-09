# pa08a – Candy Race

## Problem Description

We have a simplified race along a **1D candy-themed board** with squares numbered `1` to `30`. Each player starts at square `1` and takes turns rolling a six-sided die (values `1`–`6`). 

The square numbering:
- **Start:** Square `1`
- **End:** Square `30`

Some squares are special:
- **Boost** (if `start < end`): Land on this square and jump forward to `end`.
- **Cavity** (if `start > end`): Land on this square and get pulled backward to `end`.

If a die roll would move you **beyond** square `30`, you **do not move** on that turn. The moment a player **exactly** reaches square `30`, the game ends immediately and that player is the winner. Any remaining rolls in the input should be ignored.

Your task:  
1. **Read** the number of players, special squares, and die rolls.  
2. **Store** boost/cavity squares in a **1D array**.  
3. **Simulate** each roll in a round-robin fashion until a player wins or rolls run out.  
4. **Output** the final position of each player.

## Input Specification

- A single integer `T` indicating the number of test cases.
- For each test case:
  1. One line with three integers: `A` (players), `B` (special squares), `C` (die rolls).
  2. `B` lines, each with two integers `start end`. If `start < end`, it’s a **boost**; if `start > end`, it’s a **cavity**.
  3. `C` lines of die rolls (one integer per line, in `1..6`).

*(Alternatively, you might choose to read until EOF if you wish.)*

## Output Specification

For each test case, print the final position of each player in the format:

- Player 1 is at position X. Player 2 is at position Y. ...
- Stop any further processing immediately once a player lands on `30`.

## Functions to Implement

You must write and use **exactly** the following three functions in your solution. **Do not change** their prototypes, parameters, or return types. Document them with comments as demonstrated below.

```cpp
/**
 *  @brief Read the basic parameters of one Candy Race game.
 *
 *  Reads three integers from standard input: number of players (A),
 *  number of special squares (B), and the number of die rolls (C).
 *  If input fails (e.g., EOF reached), return false.
 *
 *  @param [out] numPlayers Reference to an int to store the number of players.
 *  @param [out] numSpecial Reference to an int for the count of special squares.
 *  @param [out] numRolls   Reference to an int for the count of die rolls.
 *
 *  @return True if successfully read a test case, false if EOF/input failure.
 */
bool readGameSetup(int &numPlayers, int &numSpecial, int &numRolls);

/**
 *  @brief Read the special squares into a board array.
 *
 *  Each line has two integers: start and end. If a player lands on
 *  'start', they immediately move to 'end'. If 'start < end',
 *  it represents a boost. If 'start > end', it's a cavity.
 *
 *  @param board An integer array of size at least 31 (indices 0..30).
 *               board[i] = 0 by default (no effect). If i is a special
 *               square, board[i] = the square to jump to.
 *  @param numSpecial The number of special squares to read from input.
 *
 *  @return void (no return value).
 */
void readSpecialSquares(int board[], int numSpecial);

/**
 *  @brief Simulate one Candy Race game, given the board and die rolls.
 *
 *  Round-robin through numPlayers. For each die roll, move the appropriate
 *  player if possible. If they land exactly on square 30, stop immediately.
 *
 *  @param board        The int array holding special square mappings.
 *  @param numPlayers   How many players are in this game.
 *  @param numRolls     How many die rolls to process.
 *  @return void (no return value). Positions should be printed to stdout.
 */
void simulateCandyRace(const int board[], int numPlayers, int numRolls);
```

## Implementation Details

Your ``main()`` function should:

1. Declare needed variables (e.g., ``board[31]`` for squares 1..30).
2. Call ``readGameSetup(...)``. If it returns true, proceed. Otherwise, stop.
3. Call ``readSpecialSquares(...)`` to fill in the board array.
4. Call ``simulateCandyRace(...)`` which should:
    - Allocate and track each player’s position in an array of ``int``.
    - Read each die roll, apply it to the correct player, update position.
    - Check for final-squares or overshoot logic.
    - Print final positions.

Because you are restricted to Chapters 1–8 (1D arrays), avoid advanced C++ features like classes, ``std::vector``, dynamic memory, etc. Use simple arrays and basic I/O from ``<iostream>``.

## Sample Input

```
1
3 2 5
3 10
6 2
3
4
5
6
3
```

## Sample Output

```
Player 1 is at position 10
Player 2 is at position 8
Player 3 is at position 2
```

*(Exact final positions will depend on how you handle each roll. Adjust your example if you want different final squares.)*

## Guidelines

- No advanced concepts: only up to arrays and basic functions.
- No forbidden statements: avoid ``continue``, ``goto``, or ``break`` outside of a ``switch``.
- One return per function.
- Keep code lines under 80 characters.
- Document your functions with the style above.

## The Judge
Test your program using The Judge:

```
$ cp /home/shared/cs135/mcastillo/pa08a/*.txt ~/cs135/pa08a/
$ judge -p ./pa08a -i pa08a-input0.txt -o pa08a-output0.txt -v
```

If your program fails any test case, review the output and make necessary fixes.

## Submission
- Name your source code file ``pa08a.cpp``.
- Run ``lint`` to check for diagnostic issues before submission.

Submit your final version using:

```
$ turnin —c cs135_[SECTION] —p pa08a —v pa08a.cpp
```