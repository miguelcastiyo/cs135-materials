# pa08b

![](https://as1.ftcdn.net/v2/jpg/11/66/67/22/1000_F_1166672282_E0FzBjAMkXxK8gfj0DPbuJvYBvx7urgo.jpg)

[TOC]

## Cyber Grid Heist

In the futuristic city of Neo-Cybertron, a group of skilled hackers, known as the "Codebreakers," are on a mission to infiltrate the city's most secure digital vault, the "Quantum Matrix." This matrix is an N x N grid, each cell safeguarding critical information represented by numbers 0 to 9. The Codebreakers must manipulate the matrix to decode and extract the information, using their expertise in executing precise operations.

Your objective is to navigate through the complex security layers of the Quantum Matrix. Each layer requires a series of operations to be performed on the grid, enabling access to deeper and more secure levels of the vault.

## Quantum Matrix Operations

There are five different types of operations:

1. **Code Shift**
   - **Command**: `row a b`
   - **Description**: Swap the entire contents of row `a` with row `b`.
   - **Details**: This operation involves exchanging every element of row `a` with the corresponding element in row `b`. Use a temporary variable to store one row's value during the swap. Ensure that the indices `a` and `b` are within the range of 1 to N.

2. **Data Channel Redirect**
   - **Command**: `col a b` 
   - **Description**: Swap the entire contents of column `a` with column `b`.
   - **Details**: Similar to row swapping, but this operation is performed vertically. Swap each element of column `a` with the corresponding element in column `b`. Remember that arrays are typically zero-indexed, so you'll need to adjust the indices accordingly.

3. **Encryption Surge**
   - **Command**: `inc`
   - **Description**: Increase each cell's value by 1, wrapping around to 0 if the value exceeds 9.
   - **Details**: Iterate through each cell of the matrix. Add 1 to the cell's value. If the result is 10, set the cell's value to 0. 

4. **Decryption Wave**
   - **Command**: `dec`
   - **Description**: Decrease each cell's value by 1, wrapping around to 9 if the value goes below 0.
   - **Details**: Similar to increment, but subtract 1 from each cell's value. If the result is -1, set the cell's value to 9. 

5. **Mirror Hack**
   - **Command**: `transpose`
   - **Description**: Convert all rows of the matrix into columns and vice-versa.
   - **Details**: Swap the element at position `[i][j]` with the element at `[j][i]`. It's important to note that you only need to loop through half of the matrix (i.e., a triangular portion) to avoid re-swapping elements.

    **Example**:
    
    ```
    1 2 3                           1 4 7
    4 5 6     after transposing     2 5 8
    7 8 9                           3 6 9
    ```

## Input specification

The input stream starts with a series of test cases. Each case begins with a positive integer N (0 < N < 10) that represents the size of the matrix. The next N lines contain N integers each. The value of each integer is in the range [0, 9]. Following this, there is a line with an integer M (M < 50). Each of the next M lines contains one operation each. If the command is `row a b` or `col a b`, then you can assume 1 <= a, b <= N, and a != b.

A single 0 on a line by itself indicates the end of the input stream. This zero should not be processed.

## Output specification

For each case, output the case number on the first line. Then on the next N lines output the content of the final matrix. Print a blank line between each case (but not after the very last one).

## Sample Input

```
4
1234
5678
1234
5678
1
transpose
3
000
111
000
2
row 1 2
inc
0
```

## Sample Output

```
Case #1
1515
2626
3737
4848

Case #2
222
111
111
```

## Program-Specific Requirements

- Ensure that your program adheres to the concepts and features introduced in the chapters covered by the course textbook. Usage of any C++ features or libraries not yet introduced in the assigned chapters (1-8) is not permitted and *may result in a zero score for the assignment*.
- Incorporate 2-dimension array(s) into your solution.
- Target no more than 35 statements (excluding blank lines and comment lines) in function `main()`. (Keep it short and simple.)
- Prototype, document, define, and use the following functions to modularize your solution. Functions should do one specific task and nothing more

    > These functions will be tested individually; please do not alter the function prototypes.

    ```cpp
    const size_t MAX = 9;  ///< Maximum dimension of a matrix.
    
    /// Swap two rows in a given matrix.
    /// @param [in,out] matrix The matrix in which rows are to be swapped.
    /// @param a The first row to be swapped (zero-based index).
    /// @param b The second row to be swapped (zero-based index).
    /// @param size The size of the matrix (number of rows/columns).
    void swap_rows(int matrix[][MAX], size_t a, size_t b, size_t size);
    
    /// Swap two columns in a given matrix.
    /// @param [in,out] matrix The matrix in which columns are to be swapped.
    /// @param a The first column to be swapped (zero-based index).
    /// @param b The second column to be swapped (zero-based index).
    /// @param size The size of the matrix (number of rows/columns).
    void swap_columns(int matrix[][MAX], size_t a, size_t b, size_t size);
    
    /// Increment each element in the matrix by 1, wrapping around to 0 at 10.
    /// @param [in,out] matrix The matrix to be incremented.
    /// @param size The size of the matrix (number of rows/columns).
    void increment_matrix(int matrix[][MAX], size_t size);
    
    /// Decrement each element in the matrix by 1, wrapping around to 9 at -1.
    /// @param [in,out] matrix The matrix to be decremented.
    /// @param size The size of the matrix (number of rows/columns).
    void decrement_matrix(int matrix[][MAX], size_t size);
    
    /// Transpose the given matrix.
    /// @param [in,out] matrix The matrix to be transposed.
    /// @param size The size of the matrix (number of rows/columns).
    void transpose_matrix(int matrix[][MAX], size_t size);
    ```

## The Judge

- Test inputs and expected outputs can be copied to your project directory:
  ```bash
  $ cp /home/shared/cs135/mcastillo/pa08b/*.txt ~/cs135/pa08b/
  ```
- Run the Judge
  ```bash
  $ judge —p pa08b —i pa08b—input0.txt —o pa08b—output0.txt —v
  ```
- If your program did not receive an "Accepted" verdict, review the output and the verdict message to identify and fix the issue in your code.
- Make necessary adjustments to your program, rerun the script, and repeat the process until you receive an "Accepted" verdict.
- There may be other sets of test inputs and expected outputs. Be sure to check your program with them all.

## Submission

- Name your source code file `pa08b.cpp`.
- Use the `lint` utility (either from within Geany or from the command line) to analyze your source code and resolve as many diagnostic issue as possible. (If uncertain about what a diagnostic message means, please ask in our Discord channel so an answer is available to all.)
- Use the following command to submit your work for grading:

```bash
$ turnin —c cs135_[SECTION] —p pa08b —v pa08b.cpp
```

## References

https://en.wikipedia.org/wiki/Matrix_(mathematics)

<!--EOF-->

