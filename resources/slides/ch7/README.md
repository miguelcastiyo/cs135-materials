---
title:  Chapter 7 - User-Defined Simple Data Types, Namespaces, and the `string` Type
author: CS 135
theme:  AnnArbor
aspectratio: 169
date:   \today

---

## Objectives (1 of 2){.shrink}

In this chapter, you will:

- Learn how to create and manipulate your own simple data type—called the enumeration type
- Explore how the assignment statement, and arithmetic and relational operators work with **enum** types
- Learn how to use **for** loops with **enum** types
- Learn how to input data into an **enum** type
- Learn how to output data stored in an **enum** type

## Objectives (2 of 2)

- Explore how to write functions to process **enum** types
- Learn how to declare variables when defining the enumeration type
- Become familiar with anonymous types
- Become familiar with the **typedef** and **using** statements 
- Learn about the **namespace** mechanism
- Explore the **string** data type, and learn how to use **string** functions to manipulate strings

## Enumeration Type (1 of 5)

- Recall that a data type is a 
    - set of values with 
    - a set of operations on them 
- **Enumeration** type is a simple data type created by the programmer
- To define an enumeration type, you need:
- A **name** for the data type
- A set of **values** for the data type
- A set of **operations** on the values

## Enumeration Type (2 of 5)

- You can specify the name and the values, but not the operations
- The syntax for enumeration type is:

    ```cpp
    enum typeName { VALUE1, VALUE2, ... };
    ```
    
- **VALUE1**, **VALUE2**, ... are identifiers called enumerators
- List specifies the ordering:

    ```cpp
    VALUE1 < VALUE2 < VALUE3 < ...
    ```

## Enumeration Type (3 of 5)

- The enumeration type is an ordered set of values
    - Default value assigned to enumerators starts at 0
- A value used in one enumeration type cannot be used by another in the same block
- Same rules apply to enumeration types declared outside of any blocks

## Enumeration Type (4 of 5){.shrink}

![](../../media/9781337102087_ppt_ch07-22.png)

![](../../media/9781337102087_ppt_ch07-18.png)

## Enumeration Type (5 of 5){.shrink}

![](../../media/9781337102087_ppt_ch07-17.png)

![](../../media/9781337102087_ppt_ch07-16.png)

## Declaring Variables

- Syntax

    ```cpp
    dataType identifier1;
    dataType identifier2;
    ```
    
- Example

    ```cpp
    enum sports { 
        BASKETBALL, FOOTBALL, HOCKEY, BASEBALL, SOCCER, VOLLEYBALL
    };
    ```
    
- Can declare variables such as:

    ```cpp
    sports popularSport;
    sports mySport;
    ```

## Assignment

- Values can be stored in enumeration data types:

    ```cpp
    popularSport = FOOTBALL;
    ```

- Stores **FOOTBALL** into **popularSport**

## Operations on Enumeration Types{.shrink}

- No arithmetic operations are allowed on enumeration types

    ```cpp
    mySport      = popularSport + 2;   // illegal 
    popularSport = FOOTBALL + SOCCER;  // illegal 
    popularSport = popularSport * 2;   // illegal
    ```

- `++` and `--` are illegal, too

    ```cpp
    popularSport++;  // illegal 
    popularSport--;  // illegal
    ```

- The solution is applying the cast operator

    ```cpp
    popularSport = FOOTBALL; 
    popularSport = static_cast<sports>(popularSport + 1);
    ```

## Relational Operators

- An enumeration type is an ordered set of values:
    - `FOOTBALL <= SOCCER` is true
    - `HOCKEY > BASKETBALL` is true
    - `BASEBALL < FOOTBALL` is false

- An enumeration type is an integral data type and can be used in loops:

    ```cpp
    for (mySport = BASKETBALL; 
         mySport <= SOCCER; 
         mySport = static_cast<sports>(mySport + 1)) { ...
    ```

This for loop has five iterations.

## Input/Output of Enumeration Types{.shrink}

- An enumeration type cannot be input/output (directly) 
- Can input and output indirectly – refer to code segments below:

    ```cpp
    enum courses {
        ALGEBRA,    BASIC,    PYTHON,    CPP, 
        PHILOSOPHY, ANALYSIS, CHEMISTRY, HISTORY
    };
    courses registered;

    switch (ch1) { 
        case 'a':
            if (ch2 == 'l') { 
                registered = ALGEBRA;
            } else { 
                registered = ANALYSIS;
            } 
            break;
    ```

## Functions and Enumeration Types

- Enumeration types can be passed as parameters to functions either by value or by reference
- A function can return a value of the enumeration type

## Declaring Variables When Defining the Enumeration Type

- Can declare variables of an enumeration type when you define an enumeration type:

    ```cpp
    enum grades { A, B, C, D, F } courseGrade;
    ```

## Anonymous Data Types (1 of 2)

- **Anonymous type** values are directly specified in the declaration, with no type name
- Example:

    ```cpp
    enum { BASKETBALL, FOOTBALL, BASEBALL, HOCKEY } mySport;
    ```

## Anonymous Data Types (2 of 2){.shrink}

- Drawbacks:
    - Cannot pass/return an anonymous type to/from a function
    - Values used in one type can be used in another, but are treated differently:

        ```cpp
        enum { ENGLISH, FRENCH, SPANISH, GERMAN, RUSSIAN } languages;
        enum { ENGLISH, FRENCH, SPANISH, GERMAN, RUSSIAN } foreignLanguages;
        ```
- This statement is illegal:

    ```cpp
    languages = foreignLanguages;  // illegal
    ```

- Best practices: to avoid confusion, 
    1. define an enumeration type first, then 
    2. declare variables

## `typedef` Statement (1 of 2)

- The **typedef** statement is used to create synonyms or aliases to a data type
- The syntax of the **typedef** statement is:

    ```cpp
    typedef existingTypeName newTypeName;
    ```
- Example:

    ```cpp
    typedef unsigned char byte;  // byte is an alias for unsigned char
    ```

- **typedef** does not create any new data types
    - Only creates an alias to an existing data type

## `using` instead of `typedef` in Modern C++ (2 of 2)

- The **using** statement is used in Modern C++ to create synonyms or aliases to a data type
- The syntax of the **using** statement is:

    ```cpp
    using newTypeName = existingTypeName;
    ```

- Example:

    ```cpp
    using byte = unsigned char;  // byte is an alias for unsigned char
    ```

- **using** does not create any new data types
- Only creates an alias to an existing data type

## Namespaces (1 of 6)

- ANSI/ISO standard C++ was officially approved in July 1998
- Most recent compilers are compatible with ANSI/ISO standard C++
- For the most part, standard C++ and ANSI/ISO standard C++ are the same
    - However, ANSI/ISO Standard C++ has some features not available in Standard C++

## Namespaces (2 of 6)

- Global identifiers in a header file used in a program become global in the program
    - A syntax error occurs if a program's identifier has the same name as a global identifier in the header file
- The same problem can occur with third-party libraries
    - Common solution: third-party vendors begin their global identifiers with _ (underscore)
    - Do not begin identifiers in your program with `_`

## Namespaces (3 of 6)

- ANSI/ISO Standard C++ attempts to solve this problem with the namespace mechanism
- The general syntax of the statement namespace is:

    ```cpp
    namespace namespace_name {
        members
    }
    ```
    
    where members consist of variable declarations, named constants, functions, or another namespace

## Namespaces (4 of 6)

![](../../media/9781337102087_ppt_ch07-9.png)

## Namespaces (5 of 6)

- A **namespace** member has scope local to the namespace
- A **namespace** member can be accessed outside the **namespace**
    - The general syntax for accessing a namespace member is:

        ```cpp
        namespace_name::identifier
        ```

    - ANSI/ISO Standard C++ provides the use of the statement using

        ```cpp
        using namespace namespace_name;
        using namespace_name::identifier;
        ```

## Namespaces (6 of 6)

- Examples with namespaces

    ```cpp
    globalType::RATE 
    using namespace globalType;
    using globalType::RATE;
    using std::cout;
    ```

- After the using statement, it is not necessary to put the namespace_name:: before the namespace member
    - Unless a namespace member and a global identifier or a block identifier have the same name!

## `std::string` Type

- To use data type **std::string**, a program must include the header file `<string>`
- A string is a sequence of zero or more characters
    - The first character is in position 0
    - The second character is in position 1, etc.
- Binary operator **+** performs the string concatenation operation
- String member function **at()** allows access to an individual character in a string with bounds checking.
<!--- Array subscript **operator[]** allows access to an individual character in a string without bounds checking-->

## Accessing each character in a `string` (1 of 2){.shrink}

```cpp
std::string msg = "?ELLO ?ORLD";

msg.at(0) = 'H';

for (std::string::size_type i = 1; i < msg.size(); ++i) {
    char ch = static_cast<char>(tolower(msg.at(i)));
    msg.at(i) = ch;
}

msg.at(6) = 'W';

msg = msg + "!";

std::cout << msg << std::endl;
```

## Accessing each character in a `string` (2 of 2){.shrink}

**Output:**

```
Hello World!
```

## Additional `string` Operations

- The data type string has a data type, `std::string::size_type`, and a named constant, `std::string::npos`, defined as follows:

    | | | 
    | - | - |
    | `std::string::size_type` | An unsigned integer (data) type |
    | `std::string::size_type` | An unsigned integer (data) type. `std::string::npos`. The maximum value of the (data) type `std::string::size_type` is a *very* large number. For example, it's `18'446'744'073'709'551'615` on the bellagio server. |

## `string functions` (1 of 2){.shrink}

![](../../media/Table07-01a.png)

## `string functions` (2 of 2){.shrink}

![](../../media/Table07-01b.png)

## Example 7-18: swap Function

![](../../media/9781337102087_ppt_ch07-24.png)

## Quick Review (1 of 3)

- Enumeration type: set of ordered values
    - Reserved word **enum** creates an enumeration type
- No arithmetic operations are allowed on the enumeration type
- Relational operators can be used with **enum** values
- Enumeration type values cannot be input or output directly
- Enumeration types can be passed as parameters to functions by value or by reference

## Quick Review (2 of 3)

- Anonymous type: a variable's values are specified without any type name
- Reserved word **typedef** creates synonyms or aliases to previously defined data types. Modern C++ uses the **using** keyword.
- The **namespace** mechanism is a feature of ANSI/ISO Standard C++
- A **namespace** member is usually a named constant, variable, function, or another namespace
- Scope of a namespace member is local to namespace

## Quick Review (3 of 3)

- **using** statement simplifies access to **namespace** members
- A **string** is a sequence of zero or more characters
- Strings in C++ are enclosed in **""**
- The first character of a string is in position 0
- An individual character can be accessed using its position number with the **at()** function.
<!--- In C++, [] is the array subscript operator-->

## Questions ???

<!--EOF--> 