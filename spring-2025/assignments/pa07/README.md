# pa07 - Basic String Manipulation

## Problem Description

In this assignment, you will create a simple C++ program that performs basic string operations using the C++ string class. You will prompt the user to enter their first and last names, then perform the following tasks:

1. Input and Concatenation:
    - Prompt the user to enter their first name and last name.
    - Concatenate the first and last names to create a full name.
    - Display the full name in the format: ``Full Name: [First Name] [Last Name]``.
2. String Length:
    - Calculate the length of the full name.
    - Display the length of the full name.
3. Uppercase Conversion:
    - Convert the full name to uppercase.
    - Display the uppercase version of the full name.
4. Name Comparison:
    - Prompt the user to enter another name.
    - Compare the new name with the full name.
    - Display whether the two names are the same or different.

## Input Specification

- The program should prompt the user to enter their first name and last name.
- The program should prompt the user to enter another name for comparison.
- All inputs should consist of alphabetic characters only. Non-alphabetic characters should be considered invalid.

## Output Specification

- Print the full name after concatenation.
- Print the length of the full name.
- Print the uppercase version of the full name.
- Print whether the names are the same or different.

## Sample Input

```
Enter your first name: John
Enter your last name: Doe
Full Name: John Doe
Length of Full Name: 8
Uppercase Full Name: JOHN DOE

Enter another name to compare: Jane Doe
The names are different.
```

## Sample Output

```
Enter your first name: Alice
Enter your last name: Cooper
Full Name: Alice Cooper
Length of Full Name: 12
Uppercase Full Name: ALICE COOPER

Enter another name to compare: Alice Cooper
The names are the same.
```

# Required Functions

```c++
/// @brief Concatenates first and last names.
/// @param firstname First name string.
/// @param lastname Last name string.
/// @return Full name after concatenation.
string getFullName(const string& firstname, const string& lastname);

/// @brief Calculates the length of the full name.
/// @param fullname The full name string.
/// @return Length of the full name.
int calculateLength(const string& fullname);

/// @brief Converts the full name to uppercase.
/// @param fullname The full name string.
/// @return Uppercase version of the full name.
string toUpperCase(const string& fullname);

/// @brief Compares two names for equality.
/// @param name1 The first name string.
/// @param name2 The second name string.
/// @return "same" if the names are equal, "different" otherwise.
string compareNames(const string& name1, const string& name2);

/// @brief Validates that the given name contains only alphabetic characters.
/// @param name The name to be validated.
/// @return True if the name is valid, false otherwise.
bool isAlphabetic(const string& name);
```

## Specific Program Requirements

- Use ``string::at()`` — do not use ``[ ]`` indexing.
- Validate alphabetic-only strings (case-insensitive).
- Use only material from Chapters 1–7.
- Each function should perform one specific task.
- Use modular functions — your solution must include and use the functions above

## Submission

```
$ turnin -c cs135_[SECTION] -p pa07 -v pa07.cpp
```
