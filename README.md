# COBOL EMPLOYEE SYSTEM

---

## Overview

---

The **COBOL EMPLOYEE SYSTEM** is a multi-program COBOL project designed to create, maintain, and update employee records using both sequential and indexed file processing techniques.

This system expands across multiple programs that work together to simulate real-world batch and online-style file maintenance. It includes initial file creation, sequential transaction processing, and indexed file maintenance with error handling. The programs demonstrate how employee data can be added, updated, deleted, and validated across different storage structures.

The system produces updated employee master files while also capturing invalid transactions for auditing and debugging purposes.

## Table of Contents

---

* [Key Functionalities](#key-functionalities)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [Running Output](#running-output)
* [Learning Outcomes](#learning-outcomes)
* [Help](#help)
* [Authors](#authors)

## Key Functionalities

---

### Multi-Program Architecture

* Includes three coordinated COBOL programs:

  * **EMPIND01** – Creates an indexed employee master file from a sequential file
  * **EMPIND02** – Maintains the indexed file using random access transactions
  * **SEQ3000** – Processes transactions sequentially to produce a new master file

* Demonstrates both batch and interactive-style processing approaches.

### Sequential File Processing

* Reads and processes:

  * **OLDEMP (sequential master file)**
  * **EMPTRAN (transaction file)**

* Uses classic merge/update logic to apply changes.

### Indexed File Processing

* Uses an indexed file (**EMPMASTI**) with:

  * Random access (EMPIND02)
  * Sequential access (EMPIND01)

* Demonstrates:

  * `READ ... INVALID KEY`
  * `WRITE`, `REWRITE`, and `DELETE`

### Transaction-Based File Maintenance

* Supports three transaction types using 88-level condition names:

  * `ADD-RECORD`
  * `CHANGE-RECORD`
  * `DELETE-RECORD`

* Applies business rules to determine valid vs invalid operations.

### Error Handling and Audit Trail

* Writes invalid or failed transactions to:

  * **ERRTRAN**
  * **ERRTRAN3**

* Uses file status codes and conditional checks to detect write failures.

### Merge/Match Logic (SEQ3000)

* Compares:

  * Transaction file vs master file using key fields

* Handles:

  * High values (end-of-file processing)
  * Matching and non-matching records
  * Controlled read sequencing using switches

### 88-Level Condition Names (Switches)

* Improves readability and control flow with flags such as:

  * `TRANSACTION-EOF`
  * `MASTER-FOUND`
  * `ALL-RECORDS-PROCESSED`
  * `NEED-TRANSACTION`
  * `WRITE-MASTER`

### Record-Level Data Handling

* Processes structured employee data including:

  * Employee ID
  * Name
  * Department Code
  * Job Class
  * Salary
  * Vacation and Sick Hours

### Modular Program Structure

* Organized into clearly defined paragraphs such as:

  * `000-MAINTAIN-EMPLOYEE-FILE`
  * `300-MAINTAIN-EMPLOYEE-RECORD`
  * `330-MATCH-MASTER-TRAN`
  * `340-WRITE-NEW-MASTER`
  * `410-APPLY-CHANGE-TRANSACTION`

* Uses **PERFORM** for structured and maintainable logic flow.

---

## Tech Stack

---

* ![COBOL](https://img.shields.io/badge/COBOL-Enterprise-blue)
* ![Visual Studio Code](https://img.shields.io/badge/VS_Code-007ACC.svg?style=for-the-badge\&logo=visual-studio-code\&logoColor=white)
* ![GitHub](https://img.shields.io/badge/GitHub-000000.svg?style=for-the-badge\&logo=GitHub)

## Installation

---

1. Clone the repository to your local machine.
2. Load the programs into your COBOL-compatible environment or mainframe emulator
3. Ensure all required input files (OLDEMP, EMPTRAN) are available

## Learning Outcomes

---

* Gained experience with both sequential and indexed file processing in COBOL
* Implemented transaction-driven file maintenance systems
* Developed merge/update logic for batch processing (SEQ3000)
* Practiced indexed file operations including READ, WRITE, REWRITE, and DELETE
* Applied 88-level condition names to improve program readability and logic control
* Built error handling mechanisms using file status codes and error files
* Strengthened understanding of multi-program system design in COBOL
* Learned differences between random and sequential access in real-world scenarios
* Improved debugging and testing techniques for file-based batch programs

## Help

---

* Ensure all input files are correctly formatted and accessible (SPACING MATTERS)
* Verify file organization types (sequential vs indexed) match program expectations
* Check file status codes for hidden runtime errors
* Restart your IDE or environment if file locks occur

## Authors

---

**Kirby Dunker**

<img src="https://github.com/KirbyD-YEAH.png" alt="Profile Picture" width="100" />

* **Kirby's GitHub Profile**: [KirbyD-YEAH](https://github.com/KirbyD-YEAH)
* **Kirby's Email**: [brdunk02@wsc.edu](mailto:brdunk@wsc.edu)

---

[Back to the top](#overview)

---
