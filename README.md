# DatabaseAssignment

## Write Queries for:
  1. List the customer name, check number, payment date and amount for the customer with customer number 1001.
  ```
SELECT customerName,checkNumber,paymentDate,amount 
FROM customers
JOIN payments
WHERE customers.customerNumber = 1001;
```
  
  
  2. List the employee number, last name and first name for all the employees  who reports to their manager with employee id 1001.
  ```
SELECT employeeNumber, lastName, firstName, reportsTo
FROM employees
WHERE reportsTo = 1001 ;
```
  
  3. List the customer name, phone and total amount of all customers with credit limit greater than 10000.
  ```
SELECT customerName, phone, SUM(payments.amount)
FROM customers
JOIN payments
ON customers.customerNumber = payments.customerNumber
WHERE creditLimit > 10000 
GROUP BY payments.amount;
```
  
  4. List all the order number, order date, product code, product name, quantity ordered, price each  for the customer with customer number 1001.
  ```
SELECT orderdetails.orderNumber, orders.orderDate, products.productCode, orderdetails.quantityOrdered, products.buyPrice
FROM orders
INNER JOIN orderdetails ON orders.orderNumber = orderdetails.orderNumber 
INNER JOIN products on orderdetails.productCode = products.productCode
WHERE orders.customerNumber = 103;
```


