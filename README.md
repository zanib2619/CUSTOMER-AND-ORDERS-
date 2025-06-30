# CUSTOMER-AND-ORDERS-

  This project demonstrates how to create *two related tables* and apply different types of SQL JOINs—INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL OUTER JOIN—to query related data effectively.

## 📁 Project Overview

In this SQL practice project, we:

1. Create two related tables: *Customers* and *Orders*
2. Establish a foreign key relationship between them
3. Use various SQL JOINs to retrieve data across these tables

This setup is useful for understanding relational databases and how different JOIN operations behave with matching and non-matching records.

This project is part of my learning and internship submission, aimed at demonstrating my understanding of database design concepts.

# 📌 Tables:
- Customers
- Orders

# 🧾 SQL Script
Creating the data
```
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(50),
    City VARCHAR(50)
);
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    Product VARCHAR(50),
    Amount DECIMAL(10, 2),
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```
Inserting the data
```
INSERT INTO Customers (CustomerID, Name, City) VALUES
(1, 'zanib', 'Delhi'),
(2, 'Kajal', 'Mumbai'),
(3, 'Fiza', 'Chennai'),
(4, 'Adnan', 'Kolkata');
```
# JOin Queries 
1. Inner JOin
```
SELECT Customers.Name, Orders.Product, Orders.Amount
FROM Customers
INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
#OUTPUT

![Screenshot 2025-06-30 171002](https://github.com/user-attachments/assets/f8978419-b6df-4991-9946-7a1040b2b0ff)

2.  LEFT JOIN
```
SELECT Customers.Name, Orders.Product, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```

#OUTPUT

![image](https://github.com/user-attachments/assets/d4e19aed-aa1e-42ab-887f-2d63a60e4855)

3. RIght JOin
```
SELECT Customers.Name, Orders.Product, Orders.Amount
FROM Customers
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
#OUTPUT

![image](https://github.com/user-attachments/assets/d735d740-9521-45b0-8564-a7997dbf0b84)

4. Full JOIN
```
SELECT Customers.Name, Orders.Product, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID

UNION

SELECT Customers.Name, Orders.Product, Orders.Amount
FROM Customers
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;


```
#OUTPUT

![image](https://github.com/user-attachments/assets/2a6962a2-76a1-46b3-b133-0a9d35260a81)




