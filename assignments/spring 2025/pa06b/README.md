# pa06a – Operation CipherDrop: Spy Network Message Decoder

## Problem Description
Welcome, Agent.
You've intercepted a stream of encrypted transmissions from an enemy network. These transmissions appear to be encoded as mathematical expressions. Your mission: decode the true message hidden within. Every expression reveals one character of the secret message when evaluated and converted to its ASCII form.
The world is counting on you. Decode wisely.

## Input Specification
Each line of input contains a binary expression:

- Two integers (operands), separated by one of five operators: +, -, *, /, or %.
- Input ends at **EOF**.

## Output Specification
For each expression, print:

- The evaluated result, right-aligned in a column of width 6.
- Followed by a space and the corresponding ASCII character, enclosed in parentheses.

## Sample Input

```
70 + 2
160 - 59 
3 * 36
216 / 2
50 + 61
200 % 167
```

Sample Output

```
    72 (H)
   101 (e)
   108 (l)
   108 (l)
   111 (o)
    33 (!)
```

## Mission Parameters (Functions to Implement)

You must use and define the following three functions exactly as specified. **DO NOT change the prototypes.**

```c++
/// @brief Read a binary expression from standard input.
/// @param [out] lhs The left operand.
/// @param [out] rhs The right operand.
/// @param [out] op The operator character.
/// @return True if input was successful, false if EOF reached.
bool read_expr(int& lhs, int& rhs, char& op);

/// @brief Evaluate the given expression.
/// @param lhs The left operand.
/// @param rhs The right operand.
/// @param op The operator character.
/// @return Result of the expression.
int eval_expr(int lhs, int rhs, char op);

/// @brief Convert an integer to its ASCII character.
/// @param value The integer value.
/// @return The corresponding ASCII character.
char to_char(int value);
```

## Programming Guidelines

- You must modularize: your ``main()`` should be clean and delegate work to the three required functions.
- Input must be read until ``EOF``, using proper loop control.
- Make sure results are right-aligned in a 6-character field using ``iomanip``.
- Adhere strictly to Chapter 6 or earlier concepts — **no arrays, vectors, structs, or classes.**

## The Judge

To validate your program, you'll use the ``judge`` utility provided on the Bellagio server. This will compare your program's output to the instructor-provided expected outputs.

- Test inputs and expected outputs can be copied to your project directory:

```
$ cp /home/shared/cs135/mcastillo/pa06a/*.txt ~/cs135/pa06a/
```

- Run the Judge

```
$ judge -p pa06a -i pa06a-input0.txt -o pa06a-output0.txt -v
```

- If your program did not receive an "Accepted" verdict, review the output and the verdict message to identify and fix the issue in your code.
- Make necessary adjustments to your program, rerun the script, and repeat the process until you receive an "Accepted" verdict.
- There may be other sets of test inputs and expected outputs. Be sure to check your program with them all.
  
## Style & Submission Requirements

- File name: ``pa06a.cpp``
- Must compile cleanly with no warnings or errors on Bellagio.
- Include the full header comment block:
- No use of forbidden features (``continue``, ``goto``, etc.)
- Run ``lint`` and resolve all diagnostics where possible.

## Submission

Submit using:
```
$ turnin -c cs135-mcastillo-[DAY] -p pa06a -v pa06a.cpp
```