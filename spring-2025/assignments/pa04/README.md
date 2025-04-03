# pa04: Distance Converter
Estimated Time to Complete: 4-6 hours

## Objective 
Write a C++ program that converts distances between kilometers, miles, and meters.

## Background
Distance Conversion Formulas:

- **Kilometers to Miles**: Miles = Kilometers × 0.621371

- **Miles to Kilometers**: Kilometers = Miles × 1.60934

- **Kilometers to Meters**: Meters = Kilometers × 1000

- **Meters to Kilometers**: Kilometers = Meters / 1000

- **Miles to Meters**: Meters = Miles × 1609.34

- **Meters to Miles**: Miles = Meters / 1609.34


## Input Description
The program should read the distance value and the distance scale from ``cin``.

## Output Description
The program should output the converted distance value in the two other scales to the terminal.

## Sample Interaction (using command-line redirection)

``` bash
$ echo 10 k | ./pa04
10 km is equivalent to:
10.00 km
6.21 mi
10000.00 m
---------------------------------------
$ echo 5 m | ./pa04
5 m is equivalent to:
5.00 km
3.11 mi
5.00 m
---------------------------------------
$ echo 15 i | ./pa04
15 mi is equivalent to:
24.14 km
15.00 mi
24142.85 m
$
```
> Note: The ``$`` character represents your shell prompt and should not be printed by your program.

## Specific Program Requirements
- Ensure that the distance input is valid and within a reasonable range.
- Implement selection structures (e.g., if, if-else, switch) in your program’s logic.
- Follow CSN Style Guide Requirements.
- Provide comments to explain your code, adhering to good coding practices.

## Algorithm

Here’s a step-by-step guide on how your program should convert distances between kilometers, miles, and meters:

1. Initialization:
    - Start by initializing variables to store the distance value, the input scale (kilometers, miles, or meters), and the converted distances for the other two scales.
2. Input:
    - Read the distance value and the input scale (k, m, or i) from the user via cin.
3. Distance Conversion:
    - Based on the input scale, convert the distance to the other two scales using the appropriate conversion formulas.
    - Use conditional statements (e.g., if, else-if, or switch) to determine which conversion formula to apply based on the input scale.
    - Apply the formulas mentioned in the Background section to perform the conversions.
    - Perform the necessary calculations and store the converted distances in the respective variables.
4. Output:
    - Output the converted distance values along with their respective scales.
    - Display the original distance value along with the scale provided by the user.
    - Display the converted distance values in the other two scales.
    - Ensure that the output is formatted clearly and accurately to avoid confusion.

## The Judge
Test inputs and expected outputs can be copied to your project directory:
``` bash
$ cp /home/shared/cs135/mcastillo/pa04/*.txt ~/cs135/pa04/
```

To run the Judge:
``` bash
$ judge —p pa04 —i pa04—input0.txt —o pa04—output0.txt —v
```

If your program did not receive an “Accepted” verdict, review the output and the verdict message to identify and fix the issue in your code. Make necessary adjustments to your program, rerun the script, and repeat the process until you receive an “Accepted” verdict.

There may be other sets of test inputs and expected outputs. Be sure to check your program with them all.

## Submission
- Name your source code file ``pa04.cpp``.
- Analyze your source code using the ``lint`` utility to resolve any diagnostic issues.
- Use the following command to submit your work for grading:

```
$turnin -c cs135_[SECTION] -p pa04 -v pa04.cpp
```

