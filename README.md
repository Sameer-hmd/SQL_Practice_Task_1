# SQL_Practice_Task_1

# 📚 Library Management System - Database Schema Design

## 📌 Task Objective
The goal of this task is to design and implement a relational database schema using a real-world domain — a **Library Management System** — by identifying entities, relationships, and creating the SQL script to define the structure.

---

## 🛠️ Tools Used
- MySQL Workbench

---

## 🧱 Schema Overview

### 🧩 Entities and Attributes:

#### 1. **Book**
- `BookID` (Primary Key)
- `Title`
- `Author`
- `Publisher`
- `YearPublished`
- `Genre`

#### 2. **Member**
- `MemberID` (Primary Key)
- `Name`
- `Email`
- `Phone`
- `JoinDate`

#### 3. **Loan**
- `LoanID` (Primary Key)
- `BookID` (Foreign Key)
- `MemberID` (Foreign Key)
- `LoanDate`
- `DueDate`
- `ReturnDate`

### 🔗 Relationships:
- A **Member** can borrow multiple **Books**
- A **Book** can be loaned to multiple **Members**
- A **Loan** table captures the many-to-many relationship

---

