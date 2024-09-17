# MySQL-Project-Library-Mng-System
MySQL Project on a Library Management System

MYSQL PROJECT - LIBRARY MANAGEMENT SYSTEM

Topic : Library Management System
Created by: NABIL MOHAMMED SHAJAHAN 

I am going to build a project named Library Management System. It keeps track of all information about books in the library, their cost, status and total number of books available in the library. 


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
