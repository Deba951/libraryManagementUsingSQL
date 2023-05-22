# OBJECTIVE: Creating a database for a library management system and performing CRUD operations on it. We'll be creating tables for books, authors, and borrowers.



<!-- ## Table Creation: -->
  
  **Author Table: **
  ```
  CREATE TABLE authors (
    author_id INT PRIMARY KEY,
    author_name VARCHAR(255)
  );
  ```

  **Books Table: **
  ```
  CREATE TABLE books (
    book_id INT PRIMARY KEY,
    title VARCHAR(255),
    author_id INT,
    FOREIGN KEY (author_id) REFERENCES authors(author_id)
  );
  ```
  
  **Borrower's Table: **
  ```
  CREATE TABLE borrowers (
    borrower_id INT PRIMARY KEY,
    borrower_name VARCHAR(255)
  );
  ```
  
  **Loans Table: **
  ```
  CREATE TABLE loans (
    loan_id INT PRIMARY KEY,
    book_id INT,
    borrower_id INT,
    loan_date DATE,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES books(book_id),
    FOREIGN KEY (borrower_id) REFERENCES borrowers(borrower_id)
  );
  ```
  
  
 ## Sample Data Insertion:
  ```
  INSERT INTO authors (author_id, author_name) VALUES (1, 'Jane Austen');
  INSERT INTO authors (author_id, author_name) VALUES (2, 'Charles Dickens');
  ```
  ```
  INSERT INTO books (book_id, title, author_id) VALUES (1, 'Pride and Prejudice', 1);
  INSERT INTO books (book_id, title, author_id) VALUES (2, 'Great Expectations', 2);
  ```
  ```
  INSERT INTO borrowers (borrower_id, borrower_name) VALUES (1, 'John Smith');
  INSERT INTO borrowers (borrower_id, borrower_name) VALUES (2, 'Emily Johnson');
  ```
  ```
  INSERT INTO loans (loan_id, book_id, borrower_id, loan_date, return_date) VALUES (1, 1, 1, '2023-01-01', '2023-01-15');
  ```
  
  
## Demo data Updation:
  ```
  UPDATE books SET title = 'Emma' WHERE book_id = 1;
  ```
  
  
## Demo data Deletion:
  ```
  DELETE FROM borrowers WHERE borrower_id = 1;
  ```
