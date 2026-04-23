\# MySQL Container Practical – INT332



\## 1. Run MySQL Container



docker run -d --name mysql-db -p 3307:3306 \\

-e MYSQL\_ROOT\_PASSWORD=root123 \\

-e MYSQL\_DATABASE=studentdb \\

mysql:8



\## 2. Connect to MySQL



docker exec -it mysql-db mysql -u root -p



Password: root123



\## 3. Use Database



USE studentdb;



\## 4. Create Table



CREATE TABLE students (

&nbsp;   id INT PRIMARY KEY,

&nbsp;   name VARCHAR(50)

);



\## 5. Insert Data



INSERT INTO students VALUES (1, 'Ankit');



\## 6. Verify Data



SELECT \* FROM students;



\## Expected Output



+----+-------+

| id | name  |

+----+-------+

| 1  | Ankit |

+----+-------+



