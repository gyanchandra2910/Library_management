# Library Management System

A comprehensive C++ application for managing library operations using MySQL database integration.

## Overview

This Library Management System is designed to help librarians efficiently manage books, members, and lending transactions in a library environment. The system provides a command-line interface with features for tracking book inventory, member records, and book lending/return operations.

## Features

- **Book Management**
  - Add new books to the library
  - Update book details (title, author, copies)
  - Remove books from the inventory
  - View complete list of available books

- **Member Management**
  - Register new library members
  - Update member information
  - Remove members from the system
  - View all registered members

- **Transaction Management**
  - Record book lending operations
  - Process book returns
  - Track lending history
  - Delete transaction records

## Database Structure

The system utilizes a MySQL database with the following tables:

1. **Books**
   - `id` (Primary Key, Auto-increment)
   - `title` (VARCHAR)
   - `author` (VARCHAR)
   - `year` (INT)
   - `copies` (INT)

2. **Lenders**
   - `id` (Primary Key, Auto-increment)
   - `name` (VARCHAR)
   - `email` (VARCHAR, Unique)
   - `phone` (VARCHAR)
   - `joined_on` (DATE)

3. **Transactions**
   - `id` (Primary Key, Auto-increment)
   - `book_id` (Foreign Key referencing books)
   - `member_id` (Foreign Key referencing lenders)
   - `date_issued` (TIMESTAMP)
   - `date_returned` (DATE, can be NULL for ongoing loans)

## Technical Requirements

- C++ compiler
- MySQL server
- MySQL C++ Connector library

## Installation and Setup

1. Install MySQL server and client libraries
2. Install the MySQL Connector/C++ development files
3. Compile the code with the MySQL libraries:
   ```
   g++ -o library_management library.cpp -lmysqlclient
   ```
4. Update the database connection parameters in the code:
   ```cpp
   mysql_real_connect(conn, "localhost", "username", "password", NULL, 3306, NULL, 0)
   ```

## Usage

Run the compiled executable to start the application. The system presents a menu-driven interface with the following options:

1. Insert a book
2. Add new member to library
3. Lend a book
4. Return a book
5. Update book details
6. Update member details
7. Delete a book
8. Delete a member
9. Delete a transaction
10. List all books
11. List all members
12. List all transactions
13. Exit

## License

This project is open for personal and educational use.

## Author

[Gyan Chandra]

---

*Last Updated: April 14, 2025*
