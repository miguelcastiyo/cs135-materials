```
REVISION HISTORY:
2024-09-10: Original  
pa02a: Music Festival Grounds Setup: Stage and Crowd Layout  
Estimated Time to Complete: 3-5 hours  
```
---

## Problem Description
In this assignment, you will write a C++ program to help plan the layout of a music festival. The program will prompt the user to enter the dimensions of the festival grounds (length and width) and the required spacing for a safety perimeter around the stages. Using predefined values for crowd capacity, the program will calculate the usable space for the crowd and the total area, including the safety perimeter.

**Note:** Your program may only use C++ features and libraries that have been covered in the first 2 chapters of the course textbook (Malik) or in lecture. Any usage of advanced features or libraries not introduced in these chapters is prohibited. This includes, but is not limited to, advanced C++ Standard Library components, language features introduced in C++ versions beyond C++14, or any third-party libraries. Further, features deprecated in C++14 shall not be used. Non-compliance with this guideline may result in a zero score for the assignment.

---

## Input Specification
- The program should prompt the user to enter the length and width of the festival grounds as floating-point values.  
- Additionally, the program should prompt the user to enter the required spacing for the safety perimeter around the stages.

---

## Output Specification
After obtaining the input, the program should perform the following calculations:
- Calculate the usable space for the crowd within the festival grounds.
- Determine the total area occupied by the festival, including the safety perimeter.

Finally, the program should display the following information:
- Usable crowd area.
- Total festival area.

---

> Note:
> 
> - The usable crowd area is calculated by subtracting twice the safety perimeter width from both the length and width of the festival grounds.
> 
>  - The total festival area is calculated without considering the safety perimeter width.

---

## Sample Interaction
```bash
$ ./a.out
Welcome to the Music Festival Grounds Layout Planner!

Enter dimensions for the festival grounds:
Length: 100.5  
Width: 75.0  

Enter the required safety perimeter width: 5.0  

Results:  
Usable crowd area: 5882.5 square meters  
Total festival area: 7537.5 square meters  
```

## Submission
Labs and programming assignments are NOT turned in using Canvas. The ``turnin`` command submits assignments to be graded.
The drop box for the assignment closes promptly at the due date/time.
If the project is enabled and you want to resubmit your assignment, you may do so by re-running the ``turnin`` command. New submissions overwrite any previous submissions.

```bash
$turnin -c cs135-mcastillo-wed -p pa02 -v pa02a.cpp
```