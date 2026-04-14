# COBOL RPT6000
___

## Overview
___
The **RPT6000** program is an enhanced COBOL reporting tool designed to process customer sales data and generate a structured, year-to-date 
sales report organized by branch and sales representative.

This version is once again expanding off the previous versions by introducing a Sales Representative Lookup Table, enhanced control break logic, and more efficient processing. It then produces a fully formatted report including customer-level detail, sales representative totals, branch totals, and grand totals. There are also calculated changes for dollar amount and percentage.

## Table of Contents
___
* [Key Functionalities](#key-functionalities)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [Running Output](#running-output)
* [Learning Outcomes](#learning-outcomes)
* [Help](#help)
* [Authors](#authors)

## Key Functionalities
___
### Multi-File Processing

* Reads from:

  * **Customer Master File (CUSTMAST)**
  * **Sales Representative File (SALESREP)**
* Demonstrates handling and coordinating multiple sequential input files.

### Sales Representative Lookup Table

* Loads sales rep data into an in-memory table using **OCCURS** and **INDEXED BY**.
* Uses **SEARCH** to match and display sales rep names dynamically.

### Control Break Processing (Multi-Level)

* Detects and handles breaks for:

  * Sales Representative
  * Branch
  * Automatically prints:

  * Sales rep totals
  * Branch totals
  * Final grand totals

### EVALUATE-Based Control Flow

* Uses the **EVALUATE TRUE** structure to simplify complex branching logic.
* Handles:

  * First record initialization
  * Control breaks
  * End-of-file processing

### 88-Level Condition Names (Switches)

* Improves readability and control flow using flags such as:

  * `CUSTMAST-EOF`
  * `SALESREP-EOF`
  * `FIRST-RECORD-SWITCH`

### Arithmetic Calculations with Error Handling

* Computes:

  * Sales change (amount)
  * Sales change (percentage)
* Uses:

  * `COMPUTE ... ROUNDED`
  * `ON SIZE ERROR`
* Handles divide-by-zero cases with `"N/A"` or overflow indicators.

### Accumulation and Roll-Up Totals

* Maintains and rolls totals across levels:

  * Customer → Sales Rep → Branch → Grand Total
* Uses `ADD` and `INITIALIZE` for accumulation and reset logic.

### Pagination and Report Formatting

* Dynamically formats report output with:

  * Page headers (date, time, page number)
  * Column headings
  * Line spacing control
* Automatically handles page breaks.

### Modular Program Structure

* Organized into clearly defined paragraphs such as:

  * `100-FORMAT-REPORT-HEADING`
  * `200-LOAD-SALESREP-TABLE`
  * `300-PREPARE-SALES-LINES`
  * `355-PRINT-SALESREP-LINE`
  * `360-PRINT-BRANCH-LINE`
  * `500-PRINT-GRAND-TOTALS`
* Uses **PERFORM** for structured, maintainable flow.

---

## Tech Stack
___
* ![COBOL](https://img.shields.io/badge/COBOL-Enterprise-blue)
* ![Visual Studio Code](https://img.shields.io/badge/VS_Code-007ACC.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
* ![GitHub](https://img.shields.io/badge/GitHub-000000.svg?style=for-the-badge&logo=GitHub)

## Installation
___
1. Clone the repository to your local machine. (or just steal my code)
2. Put the code into VS Code in your mainframe of choice

## Running Output
___
![Code Running](assets/CodeRunning.png)

## Learning Outcomes
___
 * Gained experience with COBOL file handling (sequential file processing)
 * Implemented control break logic for grouped reporting
 * Practiced data formatting and report generation in a legacy language
 * Applied arithmetic operations for business calculations (percent change, totals)
 * Improved understanding of modular programming using structured paragraphs
 * Developed skills in debugging and testing batch-style programs
 * Two-Level Summary Report: Expanded control break logic to handle multiple grouping levels (sales representative within branch), producing nested subtotals and a more detailed hierarchical report structure.
 * Switch Conditional Names (88-Level): Leveraged 88-level condition names as logical switches to improve readability and control program flow (e.g., EOF flags, first-record indicators).
 * EVALUATE Case Structure: Applied the EVALUATE statement as a case structure to streamline multi-branch decision logic, replacing complex nested IF statements.
 * SET TRUE/FALSE Statements: Used SET statements with condition names to explicitly control boolean-like flags, improving clarity and maintainability of program state management.
  
## Help
___
* Make sure compiler is running correctly.
* Potentially re-clone repository
* restart IDE

## Authors
___
**Kirby Dunker**

<img src="https://github.com/KirbyD-YEAH.png" alt="Profile Picture" width="100" />

* **Kirby's GitHub Profile**: [KirbyD-YEAH](https://github.com/KirbyD-YEAH)
* **Kirby's Email**: [brdunk02@wsc.edu](mailto:brdunk@wsc.edu)


[Back to the top](#overview)
