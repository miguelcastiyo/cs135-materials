# pa03 - Streaming Royalties Calculator

**Estimated Time to Complete: 4-5 hours**

## Problem Description

The objective of this assignment is to create a C++ program that reads streaming royalty data from an input file, including an artist's name, number of streams, and payout per stream. The program should calculate the total payout for each artist and display the information in a formatted table.

## Requirements

1. Prompt the user to enter the input filename.
2. Open the input file and read the information for three artists, with each artist's data on a separate line.
3. Parse each line to extract the artist's name, number of streams, and payout per stream.
4. Calculate the total payout for each artist.
5. Display the artist information in a formatted table with the following columns:
    - Artist Name
    - Streams 
    - Payout Per Stream
    - Total Payout

6. Use ``iomanip`` to format the output, including ``left`` and ``right`` alignment for columns. Ensure that the total payout is displayed with **two decimal places**.
Use only the ``iostream``, ``iomanip``, ``string``, and ``fstream`` headers, as necessary.

## Guidance

When reading data from a file, especially when dealing with strings that may contain spaces, it's important to use appropriate methods for parsing. The ``getline()`` function is useful for reading lines from an input stream until a specified delimiter is encountered.
To use ``getline()`` with a specified delimiter, you can provide the delimiter as the third argument. 
For example:

```c++ 
string data;
getline(inputFile, data, ',');
```

In this example, ``getline()`` will read from ``inputFile`` until it encounters a comma (,), storing the result in the string variable ``data``.

> Remember to adjust the delimiter based on your specific parsing requirements.

## Input Specification

The input file should have the following format:
- Information for three artists, with each artist's data on a separate line.
- Each line should include:
    - **Artist Name** (a string that may contain spaces).
    - A **comma** (``','``) character after the artist name.
    - **Number of Streams** (an integer).
    - **Payout Per Stream** (a floating-point number).
- Each line should be terminated with a newline character (``\n``).


## Sample Input

Example of an input file (``pa03-data0.txt``):

```
Kendrick Lamar, 18000000 0.006
Tyler, The Creator, 14000000 0.0048
Frank Ocean, 12500000 0.0055
```

## Sample Output

Example of the program's output based on the provided sample input:

```

Enter the input filename: 
Filename: pa03-data0.txt


ARTIST NAME                 STREAMS        PAYOUT PER STREAM        TOTAL PAYOUT
--------------------------------------------------------------------------------
Kendrick Lamar             18000000         $0.0060                   $108000.00
Tyler The Creator          14000000         $0.0048                   $67200.00
Frank Ocean                12500000         $0.0055                   $68750.00


```

## Sample Interaction

```
$ ./pa03

Enter the input filename: 
Filename: pa03-data0.txt


ARTIST NAME                 STREAMS        PAYOUT PER STREAM        TOTAL PAYOUT
--------------------------------------------------------------------------------
Kendrick Lamar             18000000         $0.0060                   $108000.00
Tyler The Creator          14000000         $0.0048                   $67200.00
Frank Ocean                12500000         $0.0055                   $68750.00

$
```
You can automate this a bit by using the ``echo`` command and a pipe,
e.g.,

```
$ echo pa03-data0.txt | ./pa03
```
> **Note**: The $ characters represent your shell prompt and should not be printed by your program.

## The Judge

The Judge is a program designed to evaluate and assess the correctness of your own C++ programs automatically. It does this by running your program with predefined test cases and comparing its output to the expected output.

### Step 1: Prepare Your Files
Make sure you have the following files ready:

- Your compiled program (executable).
- A file containing your test input data.
- A file containing the expected output for your program.

You can copy the test inputs and expected outputs to your project directory:

```
$ cp /home/shared/cs135/mcastillo/pa03/*.txt ~/cs135/pa03/
```

## Step 2: Run the Script
Use the following command to run the script:

```
judge —p YOUR_PROGRAM_NAME —i INPUT_DATA_FILE —o EXPECTED_OUTPUT_FILE [OPTIONS]
```

Replace the placeholders with the actual values:

- ``YOUR_PROGRAM_NAME``: The name of your compiled program.
- ``INPUT_DATA_FILE``: The name of the file containing test input data.
- ``EXPECTED_OUTPUT_FILE``: The name of the file containing expected output for comparison.
- ``[OPTIONS]``: Additional options, such as ``-v`` for verbose output.

### Example:

```
$ judge —p pa03 —i pa03-input0.txt —o pa03-output0.txt —v
```

## Step 3: Interpret the Verdict

The script will execute your program with the provided inputs and compare the actual output to the expected output. The verdict could be:

- ``AC`` (Accepted): Your output matches the expected output.
- ``PE`` (Presentation Error): Output is correct but improperly formatted.
- ``WA`` (Wrong Answer): Output does not match expected output.
- ``OLE`` (Output Limit Error): Output exceeds the allowed size.
- ``TLE`` (Time Limit Error): Program took too long to execute.
- ``RTE`` (Runtime Error): Program encountered a runtime error.
- ``MLE`` (Memory Limit Error): Program exceeded memory usage.

## Step 4: Debug and Refine
If your program does not receive an "**Accepted**" verdict, review the output and verdict message to identify and fix issues in your code. Adjust your program, rerun the script, and repeat until you receive an "**Accepted**" verdict.


## Submission

Use the following command to submit your work for grading:

```
$ turnin —c cs135_[SECTION] —p pa03 —v pa03.cpp
```