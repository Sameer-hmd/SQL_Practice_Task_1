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

## 🧾 SQL Script

The SQL script to create the above schema is included in this repository:  
**`library_schema.sql`**

```sql
CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Book (
    BookID INT PRIMARY KEY AUTO_INCREMENT,
    Title VARCHAR(255) NOT NULL,
    Author VARCHAR(255),
    Publisher VARCHAR(100),
    YearPublished INT,
    Genre VARCHAR(50)
);

CREATE TABLE Member (
    MemberID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Phone VARCHAR(15),
    JoinDate DATE
);

CREATE TABLE Loan (
    LoanID INT PRIMARY KEY AUTO_INCREMENT,
    BookID INT,
    MemberID INT,
    LoanDate DATE NOT NULL,
    DueDate DATE NOT NULL,
    ReturnDate DATE,
    FOREIGN KEY (BookID) REFERENCES Book(BookID) ON DELETE CASCADE,
    FOREIGN KEY (MemberID) REFERENCES Member(MemberID) ON DELETE CASCADE
);
