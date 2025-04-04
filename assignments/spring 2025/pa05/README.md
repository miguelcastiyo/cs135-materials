# pa05

**pa05 - Mos Eisley Cantina Expense Tracker**

## Background
Welcome to **Mos Eisley Cantina**, the most infamous watering hole in the Outer Rim! As the proprietor, you cater to smugglers, bounty hunters, rebels, and the occasional Jedi hiding from the Empire. Business is booming, but keeping track of **daily expenses** is a challenge—especially when blaster fights break out.

Your task is to write a C++ program that helps manage the cantina’s expenses efficiently. This program will track costs such as ingredient restocking, droid maintenance, bribing Imperial officers, and fixing furniture after a Wookiee fight.

## Problem Description
Your program will **read a series of positive numbers** representing expenses incurred in running the Mos Eisley Cantina and compute the following:

- Total number of expenses recorded
- Total sum of expenses
- Average expense per transaction
- Top two highest expenses (probably droid repairs or paying off bounty hunters)
- Bottom two lowest expenses (like Jawa juice refills or moisture farm water fees)

Your program should continue reading until a sentinel value of ``-1`` is entered. The sentinel value should **not** be counted in any calculations.


## Input Description
- The program will accept a **series of positive floating-point numbers**, each representing an expense in Galactic Credits.
- The sentinel value of ``-1`` indicates the end of input and should **not** be included in calculations.

## Output Description
- Display a formatted expense report styled like a Galactic Credit Statement.
- Ensure the labels are well-formatted, and values are **right-aligned** for clarity.

## Sample Interaction

```
$ echo 1250.50 345.75 7800.00 120.00 2999.99 89.50 -1 | ./pa05
Enter expenses for Mos Eisley Cantina (-1 to end):

Galactic Credit Expense Report - Mos Eisley Cantina

| Statistic                        | Value/Credits  |
|--------------------------------- |----------------|
| Total count of expenses          | 6              |
| Total sum of expenses            | 12605.74       |
| Average expense per transaction  | 2100.96        |
| Top Two Highest Expenses         | 7800.00        |
|                                  | 2999.99        |
| Bottom Two Lowest Expenses       | 89.50          |
|                                  | 120.00         |
```

## Specific Program Requirements
- Use loops (``for``, ``while``, or ``do..while``) to read expenses until ``-1`` is entered.
- Calculate and display:
    - Total count of expenses
    - Total sum of expenses
    - Average expense per transaction
    - Top two highest expenses
    - Bottom two lowest expenses
- Ensure clean and readable output formatting.

## The Judge
Test your program using The Judge:

```
$ cp /home/shared/cs135/mcastillo/pa05/*.txt ~/cs135/pa05/
$ judge -p ./pa05 -i pa05-input0.txt -o pa05-output0.txt -v
```

If your program fails any test case, review the output and make necessary fixes.

## Submission
- Name your source code file ``pa05.cpp``.
- Run lint to check for diagnostic issues before submission.

Submit your final version using:

```
$ turnin —c cs135_[SECTION] —p pa05 —v pa05.cpp
```