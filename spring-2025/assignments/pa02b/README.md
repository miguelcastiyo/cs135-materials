# pa02b: Super Bowl Ticket Investment Calculator

**Estimated Time to Complete: 4-6 hours**

# Problem Description

In this assignment, you will write a program that calculates the potential return on investment (ROI) for purchasing Super Bowl tickets. Ticket prices for the Super Bowl often **increase over time**, making them an interesting investment opportunity. Your program will ask the user for a few pieces of information and then calculate both **simple appreciation** and **compound appreciation** over a given period.

This assignment will help reinforce your understanding of **basic input, output, arithmetic operations, and working with variables.**

# Input Specifications

1. Ask the user for the **initial ticket price** (the amount paid for the ticket).
2. Ask the user for the **annual appreciation rate** (the percentage by which the ticket price increases each year).
3. Ask the user for the **number of years** they plan to hold the ticket before selling it.

# Output Specifications

Your program will calculate and display:

1. Simple Appreciation using the formula:
    $$ 
    \text{Simple Appreciation} = \text{Initial Price} \times \frac{\text{Appreciation Rate}}{100} \times \text{Years}
    $$ 

2. Compound Appreciation using the formula:
    $$
    \text{Compound Appreciation} = \text{Initial Price} \times \left(1 + \frac{\text{Appreciation Rate}}{100}\right)^{\text{Years}} - \text {Initial Price}
    $$ 

3. Finally, show the user the **total value** of the ticket after the given number of years using both appreciation models.

# Sample Interaction

```
$ ./a.out  
Welcome to the Super Bowl Ticket Investment Calculator!  

Enter the initial ticket price: 5000.00  
Enter the annual appreciation rate (as a percentage): 12.0  
Enter the number of years you plan to hold the ticket: 3  

Results  
Simple Appreciation: $1800.00  
Total Value (Simple): $6800.00  

Compound Appreciation: $2024.64  
Total Value (Compound): $7024.64  
$
```


> **Note**: The $ character represents your shell prompt and should not be printed by your program.

# Specific Program Requirements

- Use ``cin`` and ``cout`` for input and output.
- Assume users will provide valid numeric values.
- Use **variables** to store the data (initial ticket price, appreciation rate, and years) and perform the calculations.
- Format all output values to **two decimal places** using ``fixed`` and ``setprecision(2)``.
- Only utilize concepts from Malik Chapter 1 & 2 (no loops, no functions beyond ``main()``, and no arrays).

# Submission

Submit your work using the bellagio turnin command:

```
$ turnin -c cs135_[SECTION NUMBER] -p pa02b -v pa02b.cpp
```