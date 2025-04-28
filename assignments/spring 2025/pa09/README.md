# pa09 – Movie Theater Booking System

---

## Assignment Overview

For this assignment, you will design and implement a Movie Theater Booking System.

Your program will allow a user to view the theater seating chart, book a seat, cancel a booking, and display a sales summary.

This project is a capstone assignment designed to assess your mastery of all topics covered through Chapter 9.

---

## Learning Objectives

Upon successful completion of this assignment, you will be able to:

- Design and manipulate **multi-dimensional arrays**.
- Create and use **structures (structs)** to model real-world objects with multiple data members.
- Apply **loops**, **decision structures**, and **functions** effectively.
- Handle **user input validation** gracefully.
- Manage a **menu-driven** C++ program.
- Follow professional **code style**, **documentation**, and **problem-solving processes**.

---

## Program Requirements

You must write a C++ program that:

- Creates a **2D array** of **Seat** structs to represent the seating chart.
- Each **Seat** struct must track:
    - Whether the seat is **booked** (`true` if booked, `false` if available).
    - The **row number** and **seat number** (both 1-based counting).
    - The **price** of the seat.
- When the program starts:
    - Initialize every seat as **available**.
    - Set each seat’s `rowNumber`, `seatNumber`, and `price`.
- Present a **menu** to the user with the following options:
    1. **Display Seating Chart** (O for open, X for booked)
    2. **Book a Seat** (ask for row and seat number, mark as booked)
    3. **Cancel a Booking** (ask for row and seat number, mark as available)
    4. **View Sales Summary** (show number of seats sold, available, and total sales amount)
    5. **Exit** (end the program)

---

**Important Rules:**

- **Validate all user input**:
    - Menu selections must be valid.
    - Row and seat numbers must be within allowed range.
    - Cannot book an already booked seat.
    - Cannot cancel an already open seat.
- All seats must cost **$10.00**.
- You must use **modular functions** to implement each major feature.
- No global variables allowed (only constants and the seating array local to `main()`).
- Your program must handle all error cases **gracefully** (no crashes).

---

## Required Global Constants and Struct

Define the following constants and struct exactly:

```cpp
// Global constants
const int MAX_ROWS = 4;
const int MAX_SEATS = 12;
const double SEAT_PRICE = 10.00;

// Struct to represent a seat
struct Seat {
    bool isBooked;      // true if booked, false if available
    int rowNumber;      // 1-based row number
    int seatNumber;     // 1-based seat number
    double price;       // price of the seat
}
```

Each `Seat` must be properly initialized when setting up the theater.

---

## Required Functions (You Must Implement All)

You must write **all of the following functions exactly as shown**.

Each function must have a full header comment explaining its purpose, parameters, and return value.

```cpp

/**
 * Displays the current seating chart.
 * O represents an open seat, X represents a booked seat.
 *
 * @param seats The 2D array of Seat structs representing the theater.
 */
void displaySeatingChart(const Seat seats[][MAX_SEATS]);

/**
 * Books a seat for a customer if available.
 *
 * @param seats The 2D array of Seat structs.
 * @param totalSales Reference to total sales amount (updated if booking succeeds).
 * @return True if booking succeeded, false otherwise.
 */
bool bookSeat(Seat seats[][MAX_SEATS], double& totalSales);

/**
 * Cancels an existing booking.
 *
 * @param seats The 2D array of Seat structs.
 * @param totalSales Reference to total sales amount (updated if cancellation succeeds).
 * @return True if cancellation succeeded, false otherwise.
 */
bool cancelSeat(Seat seats[][MAX_SEATS], double& totalSales);

/**
 * Displays a summary report including seats sold, seats available, and total sales.
 *
 * @param seats The 2D array of Seat structs.
 * @param totalSales The total sales amount.
 */
void displaySalesSummary(const Seat seats[][MAX_SEATS], double totalSales);

/**
 * Displays the main menu and gets the user's choice.
 *
 * @return An integer representing the menu selection.
 */
int displayMenu();
```

---

## Sample Program Interaction

```
Welcome to the C++ Theater Booking System!

1. Display Seating Chart
2. Book a Seat
3. Cancel a Booking
4. View Sales Summary
5. Exit

Enter your choice: 1

SCREEN
Row 1: O O O O O O O O O O O O
Row 2: O O O O O O O O O O O O
Row 3: O O O O O O O O O O O O
Row 4: O O O O O O O O O O O O

Enter your choice: 2

Booking a seat...
Enter Row (1-4): 2
Enter Seat (1-12): 5

Seat booked successfully: Row 2, Seat 5 ($10.00)

Enter your choice: 1

SCREEN
Row 1: O O O O O O O O O O O O
Row 2: O O O O X O O O O O O O
Row 3: O O O O O O O O O O O O
Row 4: O O O O O O O O O O O O

Enter your choice: 4

Sales Summary:
Seats Sold: 1
Seats Available: 47
Total Sales: $10.00

Enter your choice: 5

Thank you for using the C++ Theater Booking System!

```

---

## Style Requirements

- One variable per line (no commas).
- Maximum line length: 80 characters.
- No global variables (only constants allowed).
- Single return statement per function (except in void functions).
- Remove all debugging output before submitting.

---

## Documentation Requirements

- Include a **header comment** at the top of your file with:
    - File Name
    - Author
    - Date
    - Academic Integrity Pledge
    - Brief Program Description
    - Time Spent
- Every function must have a full documentation comment explaining:
    - Purpose
    - Parameters
    - Return value (if applicable)
- Use **clear, descriptive names** for all variables, constants, and functions.

---

## Compilation and Submission Instructions

- Your program must compile **without warnings** on the **bellagio** server.
- Programs that do not compile will receive **zero points**, even if mostly correct.
- Only your most recent submission before the deadline will be graded.
- Late submissions are **not accepted**.

## `turnin` Command

- Use the following command to submit your work for grading:

```bash
$ turnin —c cs135_[SECTION] —p pa09 —v pa09.cpp
```

---

## Optional: Version Control with GitHub (Bonus)

Although not required for grading, you are encouraged to use GitHub to version-control your work.

**Beginner Steps:**

1. Create a GitHub account.
2. Create a new repository (example: `pa09-movie-theater`).
3. Use Git commands to track your project:
    
    ```bash
    git init
    git add pa09.cpp
    git commit -m "Initial commit"
    git remote add origin https://github.com/yourusername/pa09-movie-theater.git
    git branch -M main
    git push -u origin main
    ```
    

> **Tip:** Commit early, commit often! It will help you manage your code and prepare for future courses and internships.