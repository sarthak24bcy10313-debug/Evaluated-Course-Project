# Evaluated-Course-Project
 A Java-based command-line Personal Expense Tracker for managing, categorizing, searching, and analyzing daily expenses with CSV file storage.

 # Personal Expense Tracker

A Java-based command-line application for managing and analyzing personal expenses.

---

## 1. Project Description

The **Personal Expense Tracker** is a command-line application developed using Java. It provides a simple way for users to record and manage their daily expenses.

The application allows users to add, view, delete, search, and filter expenses. It can also calculate monthly expenditure and generate category-wise expense summaries. Expense records are stored in a CSV file so that the data can be loaded again when the application is restarted.

The project demonstrates practical implementation of Java programming concepts including object-oriented programming, collections, file handling, exception handling, input validation, date and time handling, and command-line interaction.

---

## 2. Features

The application provides the following features:

* Add a new expense
* View all expenses
* Delete an expense using its ID
* Search expenses by category or description
* Filter expenses by category
* Calculate total expenses for a selected month
* Generate category-wise expense summaries
* Sort expenses by amount
* Sort expenses by date
* Save expense records to a CSV file
* Load previously saved expenses automatically
* Validate user input
* Handle invalid input without terminating unexpectedly
* Command-line based user interface

---

## 3. Technologies Used

| Technology       | Purpose                          |
| ---------------- | -------------------------------- |
| Java             | Main programming language        |
| Java Collections | Managing expense records         |
| ArrayList        | Storing expense objects          |
| HashMap          | Generating category summaries    |
| LocalDate        | Managing expense dates           |
| File I/O         | Reading and writing expense data |
| CSV              | Persistent data storage          |
| Git              | Version control                  |
| GitHub           | Source code hosting              |

---

## 4. Requirements

Before running the project, make sure the following software is installed on your computer.

### Java Development Kit

The project requires **JDK 17 or later**.

Verify that Java is installed by opening a terminal and running:

```bash
java -version
```

Also verify the Java compiler:

```bash
javac -version
```

Example output:

```text
java version "17.x.x"
javac 17.x.x
```

A newer Java version such as Java 21 can also be used.

---

## 5. Project Structure

The repository has the following structure:

```text
expense-tracker/
│
├── README.md
├── .gitignore
│
├── src/
│   ├── Main.java
│   ├── Expense.java
│   ├── ExpenseManager.java
│   └── FileManager.java
│
└── data/
    └── expenses.csv
```

### File Description

#### `Main.java`

The entry point of the application.

It:

* Displays the main menu
* Accepts user input
* Calls the required operations
* Controls the application flow

#### `Expense.java`

Represents an individual expense.

It stores:

* Expense ID
* Date
* Category
* Amount
* Description

#### `ExpenseManager.java`

Contains the main expense-management logic.

It handles:

* Adding expenses
* Viewing expenses
* Deleting expenses
* Searching
* Filtering
* Monthly calculations
* Category summaries
* Sorting

#### `FileManager.java`

Handles persistent storage.

It is responsible for:

* Saving expenses
* Loading expenses
* Reading the CSV file
* Writing the CSV file

#### `data/expenses.csv`

Stores expense records in CSV format.

---

## 6. Installation and Setup

No external Java libraries or third-party dependencies are required.

### Step 1: Clone the Repository

Open a terminal and clone the repository:

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/YOUR-REPOSITORY-NAME.git
```

Replace `YOUR-GITHUB-USERNAME` and `YOUR-REPOSITORY-NAME` with the actual GitHub username and repository name.

Move into the project directory:

```bash
cd YOUR-REPOSITORY-NAME
```

---

### Step 2: Verify Java Installation

Run:

```bash
java -version
```

Then:

```bash
javac -version
```

Make sure JDK 17 or later is installed.

---

### Step 3: Compile the Project

From the project root directory, run:

```bash
javac -d out src/*.java
```

If compilation is successful, the compiled `.class` files will be placed inside the `out` directory.

---

## 7. Running the Application

After successful compilation, run:

```bash
java -cp out Main
```

The application will display the main menu.

Example:

```text
==========================================
       PERSONAL EXPENSE TRACKER
==========================================

--------------- MAIN MENU ---------------
1. Add Expense
2. View All Expenses
3. Delete Expense
4. Search Expenses
5. Filter by Category
6. Monthly Total
7. Category Summary
8. Sort Expenses
9. Save and Exit
------------------------------------------
Enter your choice:
```

Enter the number corresponding to the operation you want to perform.

---

## 8. Using the Application

### Add Expense

Select:

```text
1
```

The application asks for:

```text
Amount
Category
Description
Date
```

Example:

```text
Enter amount: 450
Enter category: Food
Enter description: Dinner
Enter date (YYYY-MM-DD): 2026-09-14
```

The application creates a unique expense ID.

---

### View All Expenses

Select:

```text
2
```

The application displays all available expense records.

Example:

```text
ID    Date         Category          Amount  Description
1     2026-09-14   Food              450.00  Dinner
2     2026-09-14   Transport          80.00  Bus
```

The total amount of the displayed expenses is also shown.

---

### Delete Expense

Select:

```text
3
```

Enter the ID of the expense that should be deleted.

Example:

```text
Enter expense ID to delete: 2
Expense deleted successfully.
```

---

### Search Expenses

Select:

```text
4
```

Enter a category or description.

Example:

```text
Enter category or description to search: Food
```

The application displays matching records.

---

### Filter by Category

Select:

```text
5
```

Enter the category to display.

Example:

```text
Enter category: Transport
```

Only expenses belonging to the selected category are displayed.

---

### Monthly Total

Select:

```text
6
```

Enter the required month using:

```text
YYYY-MM
```

Example:

```text
Enter month (YYYY-MM): 2026-09
```

The application calculates the total amount spent during that month.

---

### Category Summary

Select:

```text
7
```

The application calculates the total amount spent in each category.

Example:

```text
========== CATEGORY SUMMARY ==========

Food                 4500.00
Transport            1800.00
Shopping             3200.00
Bills                2000.00

======================================
```

---

### Sort Expenses

Select:

```text
8
```

The application provides sorting options:

```text
1. Sort by Amount
2. Sort by Date
```

The selected sorting method is then applied to the expense records.

---

### Save and Exit

Select:

```text
9
```

The application saves the current expense records to the CSV file and exits.

---

## 9. Data Storage

The application stores expense records in:

```text
data/expenses.csv
```

The CSV file contains the following fields:

```text
id,date,category,amount,description
```

Example:

```text
id,date,category,amount,description
1,2026-09-14,Food,450.0,Dinner
2,2026-09-14,Transport,80.0,Bus
3,2026-09-13,Shopping,1200.0,Shoes
```

The file allows the application to preserve expense information between different executions.

If the `data` directory or CSV file does not exist, the application can create the required storage location when saving data.

---

## 10. Input Validation

The application validates user input to improve reliability.

Examples of handled invalid inputs include:

* Non-numeric amount
* Zero or negative expense amount
* Invalid date
* Empty category
* Empty description
* Invalid month format
* Invalid menu selection
* Non-existent expense ID

Instead of terminating the application, an appropriate message is displayed and the user can enter the information again.

---

## 11. Example Workflow

A typical session can follow this sequence:

```text
Start Application
       |
       v
Load Existing Expenses
       |
       v
Display Main Menu
       |
       v
Add Expense
       |
       v
View Expenses
       |
       v
Search / Filter Expenses
       |
       v
Generate Monthly or Category Summary
       |
       v
Save Expenses
       |
       v
Exit Application
```

---

## 12. No External Dependencies

The project uses only standard Java libraries.

No additional libraries, frameworks, databases, or online services are required.

Therefore, dependency installation is not required beyond installing a compatible Java Development Kit.

The application can be compiled and executed directly from a terminal.

---

## 13. Troubleshooting

### `java` is not recognized

If the terminal displays an error indicating that `java` is not recognized, install a compatible JDK and ensure that Java is added to the system PATH.

Verify the installation using:

```bash
java -version
```

---

### `javac` is not recognized

The Java compiler is included with the JDK.

Make sure a **JDK**, rather than only a Java Runtime Environment, is installed.

Verify using:

```bash
javac -version
```

---

### Compilation errors

Make sure the terminal is opened in the project root directory.

The expected structure should contain:

```text
src/Main.java
src/Expense.java
src/ExpenseManager.java
src/FileManager.java
```

Then run:

```bash
javac -d out src/*.java
```

---

### Data is not displayed after restarting

Make sure the application was exited using:

```text
9. Save and Exit
```

The saved records should be present in:

```text
data/expenses.csv
```

---

## 14. Future Enhancements

Possible future improvements include:

* Graphical user interface
* Database integration
* User authentication
* Monthly budget management
* Expense charts and graphs
* Advanced filtering
* PDF and Excel report generation
* Cloud synchronization
* Multiple-user support
* Recurring expense management

---

## 15. Learning Outcomes

This project provides practical experience with:

* Java programming fundamentals
* Object-oriented programming
* Classes and objects
* Encapsulation
* Constructors and methods
* Java Collections Framework
* `ArrayList`
* `HashMap`
* Exception handling
* File input/output
* CSV data management
* Date and time handling
* Input validation
* Sorting and searching
* Command-line application development
* Git and GitHub

---

## 16. Author

**Name:** Sarthak Lokhande (24BCY10313)

**Course:** Programming in Java

**Institution:** VITyarthi / VIT

**Academic Year:** 2026

---

## 17. License

This project was developed as an academic project for the Programming in Java course.

