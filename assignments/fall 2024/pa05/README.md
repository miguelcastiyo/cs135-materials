# pa05 - Galactic Bounty Hunter Expense Tracker

## Background
You’re a renowned bounty hunter traversing the galaxy in search of high-stakes bounties and thrilling adventures. While you’re great at capturing criminals and exploring alien worlds, managing your finances across multiple planets is a bit tricky. That’s where your programming skills come in. Your task is to develop a C++ program that tracks your mission expenses, helping you stay within budget as you upgrade your spaceship, buy supplies, and pay off space pirates to leave you alone.

## Problem Description
Your program will calculate and display key financial statistics based on your expenses from recent bounty missions. These stats include the total count of expenses, the sum of expenses, the average expense per mission, the top two highest expenses (probably ship repairs or pirate bribes), and the bottom two lowest expenses (like energy drinks or fuel).

## Input Description
The program should read a series of positive numbers representing your expenses from various galactic missions using standard input (``cin``). The input will continue until you input a sentinel value of ``-1``, which indicates that your mission expenses are done. The sentinel value should not be part of the calculations.

## Output Description
Display the calculated statistics in a futuristic-looking, well-formatted table. Ensure each statistic is labeled and right-aligned for clarity

## Sample Interaction

```bash
$ echo 2300 450 3200 5000 1200 1800 -1 | ./pa05
Enter expenses for your galactic missions (-1 to end):

Galactic Bounty Hunter Expense Report

| Statistic                     | Value        |
| ------------------------------|--------------|
| Total count of expenses       |6             |
| Sum of expenses               |$13950.00     |
| Average expense per mission   |$2325.00      |
| Top Two Highest Expenses      |$5000.00      |
|                               |$3200.00      |
| Bottom Two Lowest Expenses    |$450.00       |
|                               |$1200.00      | 
$
```

## Specific Program Requirements
- Use repetition structures (e.g., ``for``, ``while``, or ``do..while`` loops) to read a series of positive numbers until the sentinel value ``-1`` is encountered.
- Calculate and display the total **count**, **sum**, **average expense per mission**, **top two highest expenses**, and **bottom two lowest expenses**.
- Ensure your program adheres to the programming concepts covered in the assigned chapters.
- Avoid using C++ features or libraries not yet introduced in the course.

## The Judge
You will find 3 sets of input files and expected outputs you can use with The Judge in the ``/home/shared/cs135/mcastillo/pa05/`` directory. Copy these files to your project directory.

``` bash
$ judge -p ./pa05 -i pa05-input0.txt -o pa05-output0.txt
```
> Note: Add the -v option to the above command for verbose output.

## Submission
Name your source code file ``pa05.cpp``. Use the ``lint`` utility to check for any diagnostic issues and resolve as many as possible.

Submit your work for grading using the command:

``` bash 
$ turnin —c cs135-mcastillo-[DAY] —p pa05 —v pa05.cpp
```