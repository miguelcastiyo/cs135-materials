# pa03 - Film Rental Program

## Objective

The objective of this assignment is to create a C++ program that reads
film information from an input file, including film title, number of
days rented, and daily rental rate. The program should calculate the
total cost for each film and display the information in a formatted
table.

## Requirements

1.  Prompt the user to enter the input filename.
2.  Open the input file and read the information for three films, with
    each film's data on a separate line.
3.  Parse each line to extract film title, number of days rented, and
    daily rental rate.
4.  Calculate the total cost for each film.
5.  Display the film information in a formatted table with the following
    columns: Film Title, Days Rented, Daily Rate, and Total Cost.
6.  Use `iomanip` to format the output, including left and right
    alignment for columns. Ensure that the total cost is displayed with
    two decimal places.
7.  Use only the `iostream`, `iomanip`, `string`, and `fstream` headers,
    as necessary.

## Guidance

When reading data from a file, especially when dealing with strings that
may contain spaces, it's important to use appropriate methods for
parsing. The `getline()` function is useful for reading lines from an
input stream until a specified delimiter is encountered.

To use `getline()` with a specified delimiter, you can provide the
delimiter as the third argument. For example:

``` c++
string data;
getline(inputFile, data, ',');
```

In this example, `getline()` will read from inputFile until it encounters
a comma (`,`), and store the result in the string variable data.

Remember to adjust the delimiter based on your specific parsing
requirements.

## Input Specification

The input file should have the following format:

-   Information for three films, with each film's data on a separate
    line.
-   Each line should include:
    -   Film Title (a string without spaces).
    -   A comma '`,`' character after the film title.
    -   Number of Days Rented (an integer).
    -   Daily Rental Rate (a floating-point number).
-   Each line should be terminated with a newline character (`\n`).

## Sample Input

Example of an input file (`pa03-data0.txt`):

```    
Barbie, 8 5.50
Inception, 5 5.00
The Godfather, 4 4.25
```

## Sample Output

Example of the program's output based on the provided sample input:

```
FILM TITLE              DAYS RENTED          DAILY RATE          TOTAL COST
--------------------------------------------------------------------------------
Barbie                           8              $5.50              $44.00
Inception                        5              $5.00              $25.00
The Godfather                    4              $4.25              $17.00
```

Please ensure that your program adheres to the specified input and
output formats and uses the given formatting guidelines. The program
should read data from the input file and write the formatted output to
the console as outlined in the assignment. User prompts should be
displayed using `cout`, and user input should be read using `cin`.

## Example Interaction

```
$ ./pa03

Enter the input filename: pa03-data0.txt
File: pa03-data0.txt

FILM TITLE              DAYS RENTED          DAILY RATE          TOTAL COST
--------------------------------------------------------------------------------
Barbie                           8              $5.50              $44.00
Inception                        5              $5.00              $25.00
The Godfather                    4              $4.25              $17.00

$
```

You can automate this a bit by using the `echo` command and a pipe,
e.g.,

``` 
$ echo pa03-data0.txt | ./pa03
```

> Note: The `$` characters represent your shell prompt and should not be printed by your program.

## The Judge

The Judge is a program designed to evaluate and assess the correctness
of your own C++ programs automatically. It does this by running your
program with predefined test cases and comparing its output to the
expected output. The Judge provides a verdict, indicating whether your
program's output is correct, contains presentation errors, or is
incorrect. You can use it to test your code and verify its correctness,
helping your identify and fix errors in your program.

### Step 1: Prepare Your Files

-   Make sure you have the following files ready:
    -   Your compiled program (executable).
    -   A file containing your test input data.
    -   A file containing the expected output for your program.
    -   Test inputs and expected outputs can be copied to your project directory: ``$ cp /home/shared/cs135/mcastillo/pa03/*.txt ~/cs135/pa03/``

### Step 2: Run the Script

-   Use the following command to run the script, specifying the
    necessary arguments:

    ```
    judge —p YOUR_PROGRAM_NAME —i INPUT_DATA_FILE —o EXPECTED_OUTPUT_FILE [OPTIONS]
    ```

    Replace the placeholders with the actual values:

    -   `YOUR_PROGRAM_NAME`: The name of your compiled program.
    -   `INPUT_DATA_FILE`: The name of the file containing test input
        data.
    -   `EXPECTED_OUTPUT_FILE`: the name of the file containing expected
        output for comparison.
    -   `[OPTIONS]`: You can include additional options if needed, for example `-v` for verbose output.

    **Example:**
    ```
    $ judge —p pa03 —i pa03—input0.txt —o pa03—output0.txt —v
    ```

### Step 3: Interpret the Verdict

-   The script will execute your program with the provided inputs and compare the actual output to the expected output.

-   It will return a verdict, which will be displayed in the terminal.
    The verdict could be one of the following:

    -   `AC` (Accepted): Your program's output matches the expected
        output.
    -   `PE` (Presentation Error): The presentation of the output is
        incorrect, but the content matches.
    -   `WA` (Wrong Answer): Your program's output does not match the
        expected output.
    -   `OLE` (Output Limit Error): Your program's output exceeded the
        allowed size.
    -   `TLE` (Time Limit Error): Your program took too long to execute.
    -   `RTE` (Run Time Error): Your program encountered a runtime
        error.
    -   `MLE` (Memory Limit Error): Your program exceeded the allowed
        memory usage.

### Step 4: Debug and Refine

-   If your program did not receive an "``Accepted``" verdict, review the
    output and the verdict message to identify and fix the issue in your
    code.
-   Make necessary adjustments to your program, rerun the script, and
    repeat the process until you receive an "``Accepted``" verdict.

## Submission

Use the following command to submit your work for grading:

```
$ turnin —c cs135-mcastillo[DAY] —p pa03 —v pa03.cpp
```
