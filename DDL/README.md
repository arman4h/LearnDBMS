A good way to review DBMS is **not by reading theory**, but by solving one large database problem step by step. Think of it as building a real database from scratch.

Here's a structured learning path that gradually introduces every DDL concept.

---

# Phase 1 - Create a Database

### Task 1

Create a database named

```sql
UniversityDB
```

Then select it.

**Concepts**

* CREATE DATABASE
* USE

---

# Phase 2 - First Table

### Task 2

Create a `Department` table.

Requirements

* Department ID
* Department Name
* Building
* Budget

Rules

* Department ID → Primary Key
* Department Name → Cannot be NULL
* Budget → Default 0

You'll learn

* CREATE TABLE
* PRIMARY KEY
* NOT NULL
* DEFAULT

---

# Phase 3 - Data Types

Create another table called `Student`.

Requirements

* Student ID
* Full Name
* Email
* Phone
* Date of Birth
* CGPA
* Gender

Choose appropriate SQL data types yourself.

Practice

* INT
* VARCHAR
* CHAR
* DATE
* DECIMAL
* FLOAT
* BOOLEAN (if supported)

---

# Phase 4 - Constraints

Modify your Student table.

Rules

* Student ID → Primary Key
* Email → Unique
* Phone → Unique
* Name → NOT NULL
* CGPA → between 0 and 4
* Gender → only M/F/O (or your chosen representation)

New concepts

* UNIQUE
* CHECK
* NOT NULL

---

# Phase 5 - Auto Increment

Modify Student ID.

Requirement

Student IDs should automatically generate.

Learn

* AUTO_INCREMENT (MySQL)
* IDENTITY (SQL Server)
* SERIAL (PostgreSQL)

---

# Phase 6 - Foreign Key

Connect Student with Department.

Every student belongs to one department.

Requirement

Add

```text
DepartmentID
```

Create the relationship.

Learn

* FOREIGN KEY
* REFERENCES

---

# Phase 7 - Another Table

Create

```text
Teacher
```

Rules

* TeacherID
* Name
* Email
* DepartmentID

Relationship

Teacher → Department

Now multiple tables point to Department.

---

# Phase 8 - Many-to-Many Relationship

A student can enroll in many courses.

A course has many students.

You cannot directly connect Student and Course.

Create

```text
Course
```

and

```text
Enrollment
```

Enrollment should contain

* StudentID
* CourseID
* Semester
* Grade

Practice

Composite Primary Key

```text
(StudentID, CourseID)
```

---

# Phase 9 - One-to-One Relationship

Create

```text
StudentProfile
```

Fields

* StudentID
* Blood Group
* Address
* Emergency Contact

StudentID should be both

* Primary Key
* Foreign Key

---

# Phase 10 - Composite Primary Key

Create

```text
Attendance
```

Columns

* StudentID
* CourseID
* Date
* Status

Primary Key

```
(StudentID, CourseID, Date)
```

---

# Phase 11 - ON DELETE Rules

Practice

```sql
ON DELETE CASCADE

ON DELETE SET NULL

ON DELETE RESTRICT
```

Observe the behavior when deleting a department or student.

---

# Phase 12 - ALTER TABLE

Practice

* Add column
* Drop column
* Rename column
* Rename table
* Add constraint
* Drop constraint

---

# Phase 13 - DROP vs TRUNCATE

Create a dummy table.

Practice

```sql
DELETE

TRUNCATE

DROP
```

Understand the difference.

---

# Phase 14 - Mini Project

Create a complete University Management database with these tables:

```
Department
Student
Teacher
Course
Enrollment
Attendance
StudentProfile
LibraryBook
BookIssue
```

Try to connect everything correctly.

---

# Final Challenge (No Hints)

Design the database for a **Bangladesh Online Food Delivery System**.

Requirements:

* Customers
* Restaurants
* Food Items
* Orders
* Order Details
* Riders
* Payments
* Reviews
* Coupons
* Delivery Addresses

Rules:

* One customer can have many orders.
* One restaurant can have many food items.
* One order can contain multiple food items.
* Riders deliver orders.
* Customers can save multiple addresses.
* Payments must be linked to orders.
* Customers can review restaurants after completing an order.
* Coupons may be applied to eligible orders.
* Decide appropriate data types and constraints yourself.
* Add primary keys, foreign keys, unique constraints, defaults, and any check constraints you think are appropriate.

---

## Recommended order to master DDL

1. `CREATE DATABASE`
2. `USE`
3. `CREATE TABLE`
4. Data types
5. `PRIMARY KEY`
6. `NOT NULL`
7. `DEFAULT`
8. `UNIQUE`
9. `CHECK`
10. `AUTO_INCREMENT`
11. `FOREIGN KEY`
12. `ON DELETE` / `ON UPDATE`
13. `ALTER TABLE`
14. `DROP`, `TRUNCATE`, `DELETE`

After be comfortable with DDL, move on to DML (`INSERT`, `UPDATE`, `DELETE`) and then queries (`SELECT`, `JOIN`, `GROUP BY`, subqueries, views, indexes, etc.).

This progression mirrors how database design is done in real-world projects and gives you repeated practice with relationships and constraints rather than isolated syntax.
