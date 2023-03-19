# SQL_HW_1

```
1. Создать таблицу employees
- id. serial,  primary key,
- employee_name. Varchar(50), not null
```
```sql
CREATE TABLE employees(
  id SERIAL PRIMARY KEY,
  employee_name VARCHAR(50) NOT NULL
);
```
```
2. Наполнить таблицу employee 70 строками.
```
```sql
INSERT INTO employees(employee_name)
VALUES
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана'),
('Олег'),
('Василий'),
('Пётр'),
('Ольга'),
('Елена'),
('Алексей'),
('Евгений'),
('Иван'),
('Людмила'),
('Светлана');
```
```
3. Создать таблицу salary
- id. Serial  primary key,
- monthly_salary. Int, not null
```
```sql
CREATE TABLE salary(
  id SERIAL PRIMARY KEY,
  monthly_salary INT NOT NULL
);
```
```
4. Наполнить таблицу salary 16 строками.
```
```sql
INSERT INTO salary(monthly_salary)
VALUES
(1000),
(1100),
(1200),
(1300),
(1400),
(1500),
(1600),
(1700),
(1800),
(1900),
(2000),
(2100),
(2200),
(2300),
(2400),
(2500);
```
```
5. Создать таблицу employee_salary
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
```
```sql
CREATE TABLE employee_salary(
  id SERIAL PRIMARY KEY,
  employee_id INT NOT NULL unique,
  salary_id INT NOT NULL,
  FOREIGN KEY (employee_id)
    REFERENCES employees(id),
  FOREIGN KEY (salary_id)
    REFERENCES salary(id)
);
```
```
6. Наполнить таблицу employee_salary 40 строками:
- в 10 строк из 40 вставить несуществующие employee_id
```
```sql
INSERT INTO employee_salary(employee_id, salary_id)
VALUES
(1, 1),
(2, 4),
(3, 9),
(4, 13),
(5, 4),
(6, 16),
(7, 10),
(8, 13),
(9, 4),
(10, 1),
(11, 7),
(12, 11),
(13, 10),
(14, 2),
(15, 3),
(16, 1),
(17, 7),
(18, 13),
(19, 4),
(20, 15),
(54, 1),
(55, 15),
(56, 14),
(57, 13),
(58, 12),
(59, 11),
(60, 10),
(61, 9),
(62, 8),
(63, 7),
(80, 1),
(81, 2),
(102, 3),
(99, 4),
(98, 5),
(103, 6),
(71, 7),
(75, 8),
(77, 3),
(90, 15);
```
```
7. Создать таблицу roles
- id. Serial  primary key,
- role_name. int, not null, unique
```
```sql
CREATE TABLE roles(
  id SERIAL PRIMARY KEY,
  role_name INT NOT NULL unique
);
```
```
8. Поменять тип столба role_name с int на varchar(30)
```
```sql
ALTER TABLE roles
ALTER COLUMN role_name
TYPE VARCHAR(30);
```
```
9. Наполнить таблицу roles 20 строками.
```
```sql
INSERT INTO roles(role_name)
VALUES
('Junior Python developer'),
('Middle Python developer'),
('Senior Python developer'),
('Junior Java developer'),
('Middle Java developer'),
('Senior Java developer'),
('Junior JavaScript developer'),
('Middle JavaScript developer'),
('Senior JavaScript developer'),
('Junior Manual QA engineer'),
('Middle Manual QA engineer'),
('Senior Manual QA engineer'),
('Project Manager'),
('Designer'),
('HR'),
('CEO'),
('Sales manager'),
('Junior Automation QA engineer'),
('Middle Automation QA engineer'),
('Senior Automation QA engineer')
```
```
10. Создать таблицу roles_employee
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
```
```sql
CREATE TABLE roles_employee(
  id SERIAL PRIMARY KEY,
  employee_id INT NOT NULL unique,
  role_id INT NOT NULL,
  FOREIGN KEY (employee_id)
    REFERENCES employees(id),
  FOREIGN KEY (role_id)
    REFERENCES roles(id)
);
```
```
11. Наполнить таблицу roles_employee 40 строками.
```
```sql
INSERT INTO roles_employee(employee_id, role_id)
VALUES
(1, 1),
(2, 4),
(3, 9),
(4, 13),
(5, 4),
(6, 16),
(7, 10),
(8, 13),
(9, 4),
(10, 1),
(11, 7),
(12, 11),
(13, 10),
(14, 2),
(15, 3),
(16, 1),
(17, 7),
(18, 13),
(19, 4),
(20, 15),
(54, 1),
(55, 15),
(56, 14),
(57, 13),
(58, 12),
(59, 11),
(60, 10),
(61, 9),
(62, 8),
(63, 7),
(70, 17),
(41, 18),
(42, 19),
(49, 20),
(48, 5),
(43, 6),
(31, 17),
(35, 18),
(37, 3),
(40, 15);
```
