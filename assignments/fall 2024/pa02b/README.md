
# pa02b: Simple Savings Interest Calculator

**Estimated Time to Complete: 4-6 hours**

## Problem Description

In this assignment, you're going to write a program that calculates interest for a savings account. Your program will ask the user for a few pieces of information and then calculate both simple and compound interest. This will help reinforce your understanding of basic input, output, and working with variables.

## Input Specifications

1. Ask the user for the **initial savings** (the amount of money they are starting with).
2. Ask the user for the **annual interest rate** (the percentage of interest earned each year).
3. Ask the user for the **number of years** the money will stay in the account.

## Output Specifications

Your program will calculate and display:

1. **Simple Interest** using the formula:
   $$
   \text{Simple Interest} = \text{Initial Savings} \times \text{Interest Rate} \times \text{Years}
   $$
   
2. **Compound Interest** using the formula:
   $$
   \text{Compound Interest} = \text{Initial Savings} \times \left(1 + \frac{\text{Interest Rate}}{100}\right)^{\text{Years}} - \text{Initial Savings}
   $$

Finally, show the user the total amount of simple and compound interest earned after the given number of years.

## Sample Interaction
```
$ ./a.out 
Welcome to the Simple Savings Interest Calculator!

Enter the initial savings amount: 2000.0 
Enter the annual interest rate (as a percentage): 5.0 
Enter the number of years: 3

Results 
Simple Interest: $300.00 
Compound Interest: $315.25 
$
```
> Note: The `$` character represents your shell prompt and should not be printed by your program.

<br>

## Specific Program Requirements

- Use `cin` and `cout` for input and output.
- Assume users will provide valid numeric values.
- Use **variables** to store the data (initial savings, interest rate, and years) and perform the calculations.
- Remember to **only utilize concepts from Malike Chapter 1 & 2**.

## Submission

Submit your work using the bellagio turnin command:

```bash
$ turnin -c cs135-mcastillo-[day] -p pa02b -v pa02b.cpp
```

