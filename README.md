# leetcode-sql-tasks
Celebal Internship Task – SQL Problems from LeetCode

1. [Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/)
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';


2. [Customer Who Never Orders] https://leetcode.com/problems/customers-who-never-order/description/

   SELECT name AS Customers
FROM Customers
WHERE id NOT IN (
  SELECT customerId FROM Orders
);


3. [Employees Earning More Than Their Managers] https://leetcode.com/problems/employees-earning-more-than-their-managers/?source=submission-ac

SELECT e.name AS Employee
FROM Employee e
JOIN Employee m ON e.managerId = m.id
WHERE e.salary > m.salary;


4. [Duplicate Emails] https://leetcode.com/problems/duplicate-emails/

SELECT email
FROM Person
GROUP BY email
HAVING COUNT(email) > 1;


5. [Second Highest Salary] https://leetcode.com/problems/second-highest-salary/

SELECT MAX(salary) AS SecondHighestSalary
FROM Employee
WHERE salary < (
  SELECT MAX(salary) FROM Employee
);

