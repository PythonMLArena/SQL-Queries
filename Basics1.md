SHOW DATABASES;   // Used to show all databases

USE "DATABASE_NAME"; // After Running this We can Perform desired operations on the Selected Database


SHOW TABLES; // Used to show/list all tables in the selected Database


CREATE DATABASE "DATABASE_NAME" ; // Create a new database

CREATE TABLE "TABLE_NAME" {
    "Column_name1" "[datatype] [keyword/constraint]" ,
    "Column_name2" "[datatype] [keyword/constraint]",
    ...
); // Create a table with column 

// Basic Table
ex. CREATE TABLE FirstTable (
    NAME VARCHAR(15),
    DoB  DATE,
    Salary DECIMAL
    )
// Advanced Table
ex. CREATE TABLE FirstTable (
    NAME VARCHAR(15) NOT NULL,
    DoB  DATE DEFAULT "1970-01-01",
    Gender ENUM("male", "female"),
    Salary DECIMAL
    )

DESC "Table_Name"; // Used to Describe the table Structure and Column Constraints 

INSERT INTO "TABLE_NAME" (col1,col2,col3)VALUES (val1,val2,val3)(val1,val2,val3),..); // Insert Data into the Table_Name according the column Names mapping col1-val1,col2-val2,col3-val3..

// Basic Table 
ex. INSERT INTO FirstTable (NAME,DoB,Salary)
VALUES ("Prathamesh","2023-04-10",100000.00); // Insert Data into table FirstTable

// Advanced Table
ex. INSERT INTO FirstTable (NAME,DoB,Gender,Salary)
VALUES ("Santosh","2023-03-08","Male",10000.00); // Insert Data into table FirstTable // Use Default Keyword instead of Date



// if you have varchar(15) and if you have put the name which have three characters only it will store only 3 character and not 15 character every time , if used char(15) It will always use 15 character.



///////////// SELECT ////////////////

SELECT "column_name" FROM "table_name";// Fetches the column values from table which is specified

ex. SELECT * FROM FirstTable; // Returns all the columns and values from the table
// Use column name instead from star to get specific column values from table ex. SELECT DOB FROM FirstTable








///////// WHERE //////////
SELECT "column_name" FROM "table_name" WHERE "Conditions";

ex. SELECT * FROM FirstTable WHERE Gender="Male"; // Returns all the Records from the table whose gender is Male

ex. SELECT * FROM FirstTable WHERE DOB='2020-01-01'; // Returns all the Records from the table whose DOB is 2020-01-01'

ex. SELECT * FROM FirstTable WHERE DOB>'2020-01-01';

ex. SELECT * FROM FirstTable WHERE
    Gender="Female" AND Dob > '2020-01-01; // Returns all the Records from the table where conditions is true

ex. SELECT * FROM FirstTable WHERE
    Gender="Female" OR Dob > '2020-01-01; // Returns all the Records from the table where conditions is true

ex. SELECT * FROM FirstTable WHERE
     NOT Gender="Female"; // Returns all the Records from the table where conditions is true








/////////////// Like ///////////


ex. SELECT * FROM FirstTable WHERE Name LIKE '%2'; // Returns all where string END  with 2

ex. SELECT * FROM FirstTable WHERE Gender LIKE 'M%'; // Returns all where string Start with M

ex. SELECT * FROM FirstTable WHERE Gender LIKE '%ale%'; // Returns all where string contains ale

ex. SELECT * FROM FirstTable WHERE Name LIKE '_a%'; // Returns all where string Start with only one character ahead of a ex. Rahul a is second in the suffix and Not Like Neha a is 4th 





//////////////////// ORDER BY AND LIMIT  AND OFFSET //////////////


ex. SELECT * FROM FirstTable ORDER BY DOB DESC; // Returns all records which are Descending Order 

ex. SELECT * FROM FirstTable ORDER BY NAME DESC LIMIT 1; // Returns all records which are Descending Order return first row only in all descenging order

ex. SELECT * FROM FirstTable WHERE Gender= 'Famale' ORDER BY NAME DESC LIMIT 1; // Returns all records which are Descending Order return first row only in all descenging order

ex. SELECT * FROM FirstTable WHERE Gender= 'Famale' ORDER BY NAME DESC LIMIT 1 OFFSET 2;
// Returns all records which are Descending Order all females but offset 2 means let say 5 records which are Descending Order so Second record will be visible.