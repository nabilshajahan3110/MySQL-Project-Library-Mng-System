# MySQL-Project-Library-Mng-System
MySQL Project on a Library Management System

MYSQL PROJECT - LIBRARY MANAGEMENT SYSTEM

Topic : Library Management System
Created by: NABIL MOHAMMED SHAJAHAN 

I am going to build a project named Library Management System. It keeps track of all information about books in the library, their cost, status and total number of books available in the library. 
Create a database named library and following TABLES in the database: 
1. Branch 2. Employee 3. Books 4. Customer 5. IssueStatus 6. ReturnStatus

CREATE DATABASE library;
USE library;

Attributes for the tables: 
1. Branch Branch_no - Set as PRIMARY KEY Manager_Id Branch_address Contact_no 
2. Employee Emp_Id – Set as PRIMARY KEY Emp_name Position Salary Branch_no - Set as FOREIGN KEY and it refer Branch_no in Branch table 
3. Books ISBN - Set as PRIMARY KEY Book_title Category Rental_Price Status [Give yes if book available and no if book not available] Author Publisher 
4. Customer Customer_Id - Set as PRIMARY KEY Customer_name Customer_address Reg_date 
5. IssueStatus Issue_Id - Set as PRIMARY KEY Issued_cust – Set as FOREIGN KEY and it refer customer_id in CUSTOMER table Issued_book_name Issue_date Isbn_book – 
Set as FOREIGN KEY and it should refer isbn in BOOKS table 
6. ReturnStatus Return_Id - Set as PRIMARY KEY Return_cust Return_book_name Return_date Isbn_book2 - Set as FOREIGN KEY and it should refer isbn in BOOKS table
Display all the tables

CREATE TABLE Branch (
    Branch_no INT PRIMARY KEY,
    Manager_Id INT,
    Branch_address VARCHAR(255),
    Contact_no VARCHAR(15)
);

INSERT INTO Branch VALUES 
(1, 101, '123 Main St', '555-1234'),
(2, 102, '456 Elm St', '555-5678'),
(3, 103, '789 Oak St', '555-7890'),
(4, 104, '321 Birch St', '555-4321'),
(5, 105, '654 Pine St', '555-6543'),
(6, 106, '987 Cedar St', '555-9876'),
(7, 107, '123 Maple St', '555-1235'),
(8, 108, '456 Ash St', '555-5679'),
(9, 109, '789 Willow St', '555-7891'),
(10, 110, '321 Poplar St', '555-4322'),
(11, 111, '654 Fir St', '555-6544'),
(12, 112, '987 Spruce St', '555-9877'),
(13, 113, '123 Cypress St', '555-1236'),
(14, 114, '456 Redwood St', '555-5680'),
(15, 115, '789 Sequoia St', '555-7892'),
(16, 116, '321 Dogwood St', '555-4323'),
(17, 117, '654 Elmwood St', '555-6545'),
(18, 118, '987 Magnolia St', '555-9878'),
(19, 119, '123 Hawthorn St', '555-1237'),
(20, 120, '456 Chestnut St', '555-5681'),
(21, 121, '789 Sycamore St', '555-7893'),
(22, 122, '321 Juniper St', '555-4324'),
(23, 123, '654 Laurel St', '555-6546'),
(24, 124, '987 Aspen St', '555-9879'),
(25, 125, '123 Willow Ave', '555-9988');

CREATE TABLE Employee (
    Emp_Id INT PRIMARY KEY,
    Emp_name VARCHAR(100),
    Position VARCHAR(50),
    Salary DECIMAL(10, 2),
    Branch_no INT,
    FOREIGN KEY (Branch_no) REFERENCES Branch(Branch_no)
);

INSERT INTO Employee VALUES
(1, 'John Doe', 'Manager', 60000, 4),
(2, 'Jane Smith', 'Assistant Manager', 45000, 2),
(3, 'David Brown', 'Librarian', 40000, 1),
(4, 'Mary Johnson', 'Assistant Librarian', 35000, 4),
(5, 'Emily Davis', 'Library Assistant', 30000, 3),
(6, 'Michael Wilson', 'Library Clerk', 28000, 5),
(7, 'James Taylor', 'IT Support', 42000, 1),
(8, 'Sarah Lee', 'Library Assistant', 31000, 3),
(9, 'Robert Miller', 'Library Clerk', 29000, 6),
(10, 'Laura Moore', 'Manager', 62000, 2),
(11, 'Patricia White', 'Librarian', 43000, 1),
(12, 'Daniel Harris', 'Assistant Librarian', 34000, 2),
(13, 'Christopher Martin', 'Library Assistant', 29500, 4),
(14, 'Angela Jackson', 'Library Clerk', 28500, 6),
(15, 'Lisa Thompson', 'Assistant Manager', 45500, 3),
(16, 'Anthony Martinez', 'IT Support', 41500, 5),
(17, 'Betty Clark', 'Manager', 61000, 1),
(18, 'Charles Lewis', 'Library Assistant', 30000, 2),
(19, 'Karen Walker', 'Librarian', 42000, 6),
(20, 'Joseph Allen', 'Library Clerk', 29000, 2),
(21, 'Susan Young', 'Assistant Librarian', 35000, 4),
(22, 'Linda King', 'Library Clerk', 28000, 5),
(23, 'Brian Wright', 'Manager', 60000, 6),
(24, 'Nancy Hill', 'Librarian', 41000, 2),
(25, 'Lucas Brown', 'Library Assistant', 35000, 1);
CREATE TABLE Books (
    ISBN VARCHAR(20) PRIMARY KEY,
    Book_title VARCHAR(255),
    Category VARCHAR(100),
    Rental_Price DECIMAL(5, 2),
    Status VARCHAR(3),
    Author VARCHAR(100),
    Publisher VARCHAR(100)
);

INSERT INTO Books VALUES
('978-3-16-148410-0', 'Introduction to MySQL', 'Database', 15.99, 'Yes', 'Author A', 'Publisher A'),
('978-1-56619-909-4', 'Learning SQL', 'Database', 17.99, 'No', 'Author B', 'Publisher B'),
('978-0-596-52068-7', 'Mastering Database Design', 'Database', 18.99, 'Yes', 'Author C', 'Publisher C'),
('978-1-4028-9462-6', 'Advanced SQL Queries', 'Database', 25.99, 'Yes', 'Author D', 'Publisher D'),
('978-0-321-48681-3', 'Database Systems', 'Computer Science', 35.99, 'No', 'Author E', 'Publisher E'),
('978-1-4919-1889-0', 'Python for Data Science', 'Programming', 45.99, 'Yes', 'Author F', 'Publisher F'),
('978-1-4493-8970-4', 'Learning Python', 'Programming', 50.99, 'Yes', 'Author G', 'Publisher G'),
('978-0-201-63451-2', 'Algorithms', 'Computer Science', 30.99, 'No', 'Author H', 'Publisher H'),
('978-1-118-43467-9', 'Artificial Intelligence', 'Computer Science', 55.99, 'Yes', 'Author I', 'Publisher I'),
('978-0-07-178368-7', 'Introduction to Networking', 'Computer Networks', 22.99, 'Yes', 'Author J', 'Publisher J'),
('978-0-387-95284-6', 'Cybersecurity Fundamentals', 'Computer Networks', 32.99, 'Yes', 'Author K', 'Publisher K'),
('978-0-521-86538-6', 'Operating Systems', 'Computer Science', 40.99, 'No', 'Author L', 'Publisher L'),
('978-1-59327-599-0', 'The Linux Command Line', 'Operating Systems', 39.99, 'Yes', 'Author M', 'Publisher M'),
('978-1-4919-4547-6', 'JavaScript: The Good Parts', 'Programming', 23.99, 'Yes', 'Author N', 'Publisher N'),
('978-0-596-51979-6', 'Designing Web APIs', 'Web Development', 29.99, 'No', 'Author O', 'Publisher O'),
('978-1-59327-290-6', 'Python Crash Course', 'Programming', 27.99, 'Yes', 'Author P', 'Publisher P'),
('978-0-12-802902-9', 'Computer Networks', 'Computer Networks', 49.99, 'No', 'Author Q', 'Publisher Q'),
('978-1-4919-0370-4', 'High Performance MySQL', 'Database', 55.99, 'Yes', 'Author R', 'Publisher R'),
('978-0-262-03384-8', 'Introduction to Algorithms', 'Computer Science', 65.99, 'No', 'Author S', 'Publisher S'),
('978-1-59327-891-5', 'Shell Scripting', 'Operating Systems', 45.99, 'Yes', 'Author T', 'Publisher T'),
('978-1-59327-424-5', 'Web Development with Node.js', 'Web Development', 33.99, 'No', 'Author U', 'Publisher U'),
('978-0-13-438998-2', 'The Pragmatic Programmer', 'Programming', 39.99, 'Yes', 'Author V', 'Publisher V'),
('978-0-321-48681-2', 'Operating Systems: Internals and Design Principles', 'Computer Science', 41.99, 'Yes', 'Author W', 'Publisher W'),
('978-0-13-477102-3', 'Database Management Systems', 'Database', 49.99, 'Yes', 'Author X', 'Publisher X'),
('978-1-118-83835-9', 'Computer Science: An Overview', 'Computer Science', 60.99, 'Yes', 'Author Y', 'Publisher Y');

CREATE TABLE Customer (
    Customer_Id INT PRIMARY KEY,
    Customer_name VARCHAR(100),
    Customer_address VARCHAR(255),
    Reg_date DATE
);

INSERT INTO Customer VALUES
(1, 'Alice Johnson', '789 Maple St', '2021-09-01'),
(2, 'Bob Williams', '456 Oak St', '2022-08-02'),
(3, 'Carol Taylor', '123 Pine St', '2023-07-03'),
(4, 'Daniel Anderson', '987 Cedar St', '2024-06-04'),
(5, 'Emily Scott', '654 Birch St', '2021-06-05'),
(6, 'Frank White', '321 Elm St', '2022-06-06'),
(7, 'Grace Lee', '123 Maple St', '2023-05-07'),
(8, 'Harry Walker', '456 Oak St', '2024-04-08'),
(9, 'Irene Miller', '789 Pine St', '2021-03-09'),
(10, 'James Clark', '987 Cedar St', '2022-03-10'),
(11, 'Karen Wright', '654 Birch St', '2023-02-11'),
(12, 'Larry Young', '321 Elm St', '2024-02-12'),
(13, 'Maria Thompson', '123 Maple St', '2021-01-13'),
(14, 'Nancy Jackson', '456 Oak St', '2022-01-01'),
(15, 'Oliver Harris', '789 Pine St', '2023-12-15'),
(16, 'Patricia King', '987 Cedar St', '2024-12-16'),
(17, 'Quincy Lewis', '654 Birch St', '2021-11-17'),
(18, 'Rebecca Martin', '321 Elm St', '2022-11-18'),
(19, 'Samuel Allen', '123 Maple St', '2023-11-19'),
(20, 'Tina Nelson', '456 Oak St', '2024-10-20'),
(21, 'Ursula Baker', '789 Pine St', '2021-10-21'),
(22, 'Victor Perez', '987 Cedar St', '2022-10-22'),
(23, 'Wendy Rivera', '654 Birch St', '2022-09-23'),
(24, 'Xavier Brooks', '321 Elm St', '2023-07-24'),
(25, 'Yvonne Bennett', '123 Maple St', '2021-07-25');

CREATE TABLE IssueStatus (
    Issue_Id INT PRIMARY KEY,
    Issued_cust INT,
    Issued_book_name VARCHAR(255),
    Issue_date DATE,
    Isbn_book VARCHAR(20),
    FOREIGN KEY (Issued_cust) REFERENCES Customer(Customer_Id),
    FOREIGN KEY (Isbn_book) REFERENCES Books(ISBN)
);

INSERT INTO IssueStatus VALUES
(1, 1, 'Introduction to MySQL', '2021-01-01', '978-3-16-148410-0'),
(2, 2, 'Learning SQL', '2022-01-02', '978-1-56619-909-4'),
(3, 3, 'Mastering Database Design', '2023-02-03', '978-0-596-52068-7'),
(4, 4, 'Advanced SQL Queries', '2024-02-04', '978-1-4028-9462-6'),
(5, 5, 'Database Systems', '2021-03-05', '978-0-321-48681-3'),
(6, 6, 'Python for Data Science', '2022-03-06', '978-1-4919-1889-0'),
(7, 7, 'Learning Python', '2023-04-07', '978-1-4493-8970-4'),
(8, 8, 'Algorithms', '2024-04-08', '978-0-201-63451-2'),
(9, 9, 'Artificial Intelligence', '2021-05-09', '978-1-118-43467-9'),
(10, 10, 'Introduction to Networking', '2022-05-10', '978-0-07-178368-7'),
(11, 11, 'Cybersecurity Fundamentals', '2023-06-11', '978-0-387-95284-6'),
(12, 12, 'Operating Systems', '2024-06-12', '978-0-521-86538-6'),
(13, 13, 'The Linux Command Line', '2021-07-13', '978-1-59327-599-0'),
(14, 14, 'JavaScript: The Good Parts', '2022-07-14', '978-1-4919-4547-6'),
(15, 15, 'Designing Web APIs', '2023-08-15', '978-0-596-51979-6'),
(16, 16, 'Python Crash Course', '2024-08-16', '978-1-59327-290-6'),
(17, 17, 'Computer Networks', '2021-09-17', '978-0-12-802902-9'),
(18, 18, 'High Performance MySQL', '2022-09-18', '978-1-4919-0370-4'),
(19, 19, 'Introduction to Algorithms', '2023-10-19', '978-0-262-03384-8'),
(20, 20, 'Shell Scripting', '2024-10-20', '978-1-59327-891-5'),
(21, 21, 'Web Development with Node.js', '2021-11-21', '978-1-59327-424-5'),
(22, 22, 'The Pragmatic Programmer', '2022-11-22', '978-0-13-438998-2'),
(23, 23, 'Operating Systems: Internals and Design Principles', '2022-12-23', '978-0-321-48681-2'),
(24, 24, 'Database Management Systems', '2023-12-24', '978-0-13-477102-3'),
(25, 25, 'Computer Science: An Overview', '2024-12-25', '978-1-118-83835-9');

CREATE TABLE ReturnStatus (
    Return_Id INT PRIMARY KEY,
    Return_cust INT,
    Return_book_name VARCHAR(255),
    Return_date DATE,
    Isbn_book2 VARCHAR(20),
    FOREIGN KEY (Return_cust) REFERENCES Customer(Customer_Id),
    FOREIGN KEY (Isbn_book2) REFERENCES Books(ISBN)
);

INSERT INTO ReturnStatus VALUES
(1, 1, 'Introduction to MySQL', '2021-01-10', '978-3-16-148410-0'),
(2, 2, 'Learning SQL', '2022-01-12', '978-1-56619-909-4'),
(3, 3, 'Mastering Database Design', '2023-01-14', '978-0-596-52068-7'),
(4, 4, 'Advanced SQL Queries', '2024-02-16', '978-1-4028-9462-6'),
(5, 5, 'Database Systems', '2021-02-18', '978-0-321-48681-3'),
(6, 6, 'Python for Data Science', '2022-03-20', '978-1-4919-1889-0'),
(7, 7, 'Learning Python', '2023-03-22', '978-1-4493-8970-4'),
(8, 8, 'Algorithms', '2024-04-24', '978-0-201-63451-2'),
(9, 9, 'Artificial Intelligence', '2021-04-26', '978-1-118-43467-9'),
(10, 10, 'Introduction to Networking', '2022-05-28', '978-0-07-178368-7'),
(11, 11, 'Cybersecurity Fundamentals', '2023-05-30', '978-0-387-95284-6'),
(12, 12, 'Operating Systems', '2024-06-01', '978-0-521-86538-6'),
(13, 13, 'The Linux Command Line', '2021-06-02', '978-1-59327-599-0'),
(14, 14, 'JavaScript: The Good Parts', '2022-07-03', '978-1-4919-4547-6'),
(15, 15, 'Designing Web APIs', '2023-07-04', '978-0-596-51979-6'),
(16, 16, 'Python Crash Course', '2024-08-05', '978-1-59327-290-6'),
(17, 17, 'Computer Networks', '2021-08-06', '978-0-12-802902-9'),
(18, 18, 'High Performance MySQL', '2022-09-07', '978-1-4919-0370-4'),
(19, 19, 'Introduction to Algorithms', '2023-09-08', '978-0-262-03384-8'),
(20, 20, 'Shell Scripting', '2024-10-09', '978-1-59327-891-5'),
(21, 21, 'Web Development with Node.js', '2021-10-10', '978-1-59327-424-5'),
(22, 22, 'The Pragmatic Programmer', '2021-11-11', '978-0-13-438998-2'),
(23, 23, 'Operating Systems: Internals and Design Principles', '2022-11-12', '978-0-321-48681-2'),
(24, 24, 'Database Management Systems', '2023-12-13', '978-0-13-477102-3'),
(25, 25, 'Computer Science: An Overview', '2023-12-14', '978-1-118-83835-9');

SELECT * FROM Branch;
SELECT * FROM Employee;
SELECT * FROM Books;
SELECT * FROM Customer;
SELECT * FROM IssueStatus;
SELECT * FROM ReturnStatus;

       


 ![MP Branch](https://github.com/user-attachments/assets/47ddf19b-0342-42ec-aef5-f1b8969ab65f)


 
![MP Employee](https://github.com/user-attachments/assets/69154e82-5779-4b28-a67a-f5556b8ba50a)



![MP Books](https://github.com/user-attachments/assets/1442abdf-aeaf-4859-9f3c-37951f8f7184)



![MP Customer](https://github.com/user-attachments/assets/1eec0b0f-96a6-4272-bbf4-f39c6ed325ba)
 

 
![MP IssueStatus](https://github.com/user-attachments/assets/d0eb4bec-d6ee-4a2b-905b-f5b7a9ae3a4f)



![MP ReturnStatus](https://github.com/user-attachments/assets/d2fbed0e-a534-4513-9198-28f9943c2642)




1. Retrieve the book title, category, and rental price of all available books.

SELECT Book_title, Category, Rental_Price
FROM Books WHERE Status = 'Yes';

 

![MP 1](https://github.com/user-attachments/assets/b3e25c46-16ec-43a1-955e-f65ecbcd36f9)



2. List the employee names and their respective salaries in descending order of salary.

SELECT Emp_Id, Emp_name, 
Salary FROM Employee 
ORDER BY Salary DESC;



![MP 2](https://github.com/user-attachments/assets/1705314d-29bf-40d6-87ba-fe63757a3bb5)


  
3. Retrieve the book titles and the corresponding customers who have issued those books.

SELECT IssueStatus.Issued_cust, 
IssueStatus.Issued_book_name, 
Customer.Customer_name
FROM IssueStatus LEFT JOIN Customer 
ON IssueStatus.Issued_cust = Customer.Customer_Id;

 

![MP 3](https://github.com/user-attachments/assets/ffc65820-8228-4e9d-b90b-319be9750ae4)




4. Display the total count of books in each category.

SELECT Category, 
COUNT(*) AS NoOfBooks
FROM Books GROUP BY 
Category;



![MP 4](https://github.com/user-attachments/assets/ca98b0fe-1ffe-4ce2-a451-7c3df70911c5)


 

5. Retrieve the employee names and their positions for the employees whose salaries are above Rs.50,000.

SELECT Emp_name, 
Position, Salary
FROM Employee WHERE 
Salary > 50000;



![MP 5](https://github.com/user-attachments/assets/c5174cb7-fa29-4b2d-a815-694f09ba128b)


 
6. List the customer names who registered before 2022-01-01 and their issued books.

SELECT Customer.Reg_date, Customer.Customer_name, 
IssueStatus.Issued_book_name FROM Customer
LEFT JOIN IssueStatus ON 
Customer.Customer_Id = IssueStatus.Issued_cust
WHERE Customer.Reg_date < '2022-01-01';

 

![MP 6](https://github.com/user-attachments/assets/7e52a1b3-c8e1-4a48-8fcb-5b314b3a3be3)



7. Display the branch numbers and the total count of employees in each branch.

SELECT Branch_no, 
COUNT(*) AS NoOfEmployees
FROM Employee 
GROUP BY Branch_no;



![MP 7](https://github.com/user-attachments/assets/28a65d64-91de-4b3d-bb27-c9f9d832a010)

 
 
8. Display the names of customers who have issued books in the month of June 2023.

SELECT Customer.Customer_name,
IssueStatus.Issued_book_name, 
IssueStatus.Issue_date
FROM Customer LEFT JOIN IssueStatus 
ON Customer.Customer_Id = IssueStatus.Issued_cust
WHERE IssueStatus.Issue_date 
BETWEEN '2023-06-01' AND '2023-06-30';
 
 

![MP 8](https://github.com/user-attachments/assets/0009632d-e10f-4002-b987-43912172bfbd)



9. Retrieve book titles from books table containing database.

SELECT ISBN, Book_title, Author
FROM Books WHERE Category = 'Database'
ORDER BY ISBN;



![MP 9](https://github.com/user-attachments/assets/08e68b45-2dd6-4846-b14d-ab9d7d4d9983)


 
10.Retrieve the branch numbers along with the count of employees for branches having more than 4 employees.

SELECT Branch_no, 
COUNT(*) AS NoOfEmployees
FROM Employee 
GROUP BY Branch_no
HAVING COUNT(*) > 4;
 
 

![MP 10](https://github.com/user-attachments/assets/3f38014b-3c81-4d9c-92d5-e161697a8011)



11. Retrieve the names of employees who manage branches and their respective branch addresses.

SELECT Employee.Emp_name, 
Employee.Branch_no, 
Branch.Branch_address
FROM Employee LEFT JOIN Branch ON
Employee.Branch_no = Branch.Branch_no
WHERE Employee.Position = 'Manager'
ORDER BY Branch_no;



![MP 11 A](https://github.com/user-attachments/assets/ea38397b-cc13-4ed9-9a8d-8a85da93c499)

 

12. Display the names of customers who have issued books with a rental price higher than Rs. 25.

SELECT Customer.Customer_name, Books.Book_title, 
Books.Rental_Price
FROM Customer INNER JOIN IssueStatus
ON Customer.Customer_Id = IssueStatus.Issued_cust
INNER JOIN Books ON
IssueStatus.Isbn_book = Books.ISBN
WHERE Books.Rental_Price > 25;


 
![MP 12](https://github.com/user-attachments/assets/5018b098-e8f4-4ae8-b67b-0b3ff68fbe39)
