# A3 Databases review 
## Questions review 
### Question 1. 
A telecommunications company is designing a relational database to store its desk tickets.  
The database will have the following tables:

- Operator(OperatorID, OperatorName, Location)  
- Engineer(EngineerID, EngFirstName, EngLastName, EngLocation, Salary)  
- Ticket(TicketNo, Location, Status, OperatorID, TicketDate, TicketPriority)  
- Supplier(SupplierID, Email, PhoneNo)  
- Product(ProductID, ProductName, Price, SupplierID)  
- ProductOrder(TicketNo, OrderID, ProductID, Quantity, EngineerID)  

#### a. Identify the primary key for each of the tables described above. [3]
The primary key for each table above is:
 1. Operator: OperatorID
 2. Engineer: EngineerID
 3. Ticket: TicketNo
 4. Supplier: SupplierID 
 5. Product: ProductID
 6. ProductOrder: TicketNo

The primary key of table can be identified as it will be the unique identifier for each table. Such as Operator ID will uniquely identify the tuples of the table operator and so on. 

#### b. Identify three benefits of a relational database. [3]

[A realtional database is a collection of data points into tables with rows and columns, allowing them to be related to one another. A relational database is built using a structured query language (SQL) and ensures high data integrity(data reliability, data accuracy, data consistency, data completness)]


--- 
The usage of relational databases ensures high data integrity, scalability and consistancy through a structured format and ACID compliance. 

Firstly, realtional databases ensures high data integrity through organizing data in tables with fixed columns (attributes) and rows (tuples). High data integrity is maintained through different levels of schemas used to construct the tables. By establishing elements like the primary key which unqiuely identify each record in a table, foreign keys that are columns in a table that are referenced from other tables and prevent overlapping data values and consitraints like 'not null' to ensure a attribute has a correspond value and 'unqiue' that ensures a value of a column does not repeat in rows. 

Secondaly, data accuracy is ensured through 

--- 

The usage of relational databases ensure data accuracy, improved data secuirity and easy data retrieval. 

Firstly, data accuracy is established in relatioanl databases through rules such as primary and foriegn keys, and constraints that ensure invalid data from being entered. 

Secondly, data security allows onyl authrooized users to access and modify records of tables through database management systems that regulate realtional databases. 

And finally, through the structured query language(SQL) of relational database, records from table can easily be retrieved, modified and added to tables. 
#### c. Construct an ERD for the relational database. [3]


#### d. Construct the SQL DDL instructions to create the Ticket table. [1]

``` SQL 
CREATE TABLE ticket (TicketNo INT primary key,
                    location1 VARCHAR(255),
                    Status1 VARCHAR(30),
                    OperatorID INT,  
                    TicketDate DATE, 
                    TicketPriority INT, 

                    constraint ticket_fk
                    foreign key (OperatorID)
                    references Operator(OperatorID)
                    );
```

#### e. Construct the SQL DML statements to return the total product quantity ordered by the engineer with the engineer ID D893. [4]

```SQL 
SELECT SUM(quantity) AS total_product
FROM ProductOrder
WHERE EngineerID = 'D893'; 
```


#### f. Identify a foreign key in the Product table. [1]
A foreign key in the product table would be supplierID which is the primary key of the supplier table. 

#### g. State whether the database is normalized and whether it is in third normal form (3NF). [1]
The database is noramalized as every table have a primary key that each attribute is dependent on the key and only the key. The database is also in third normal form (3NF) as there is no transitive dependent between non-key attributes. 

#### h. Describe the characteristics of a database that is in third normal form (3NF). [3]
A database that is characterised as in third normal form (3NF) is in 1NF and 2NF, and contains no transitive dependency. This means that all non-key attributes depend on only the keys and no non-key attributes. 


### The following table is an example of the **Engineer** table:

| EngineerID | EngFirstName | EngLastName | EngLocation | Salary |
|-----------|-------------|-------------|-------------|--------|
| D893 | Daniel | Buchidan | Trier | 7000 |
| D894 | Constantin | Constantin | Heidelberg | 6000 |
| D895 | Martin | Bond | Cologne | 6500 |

#### i. Define the term *tuple*. Give an example of a tuple from the Engineer table. [2]
A tuples is a record input into the database that represents information corresponding to each attribute of a table. From the engineering table provided above, a tuple would be the record of engineer Martin Bond, whose Engieer ID, first name, last name, location and salary are provided and stored in the engineer table.

#### j. State the number of fields in the Engineer table. [1]
The number of fields are 5. 

#### k. Construct an SQL statement to increase the salary of the engineer with the ID D894 by 300. [2]

```SQL 
UPDATE engineer 
SET salary = salary+300 
WHERE EngineerID= 'D894';
```

#### l. Construct SQL statements to update the Engineer table to include two more fields:  
- one called `Experience`, to store how many years of experience each engineer has  
- one called `IncreaseDate`, which includes the date when the last salary raise occurred  

[4]

```SQL 
ALTER TABLE engineer 
ADD COLUMN experience INT, 
            IncreaseDate DATE 
;
```

#### m. Construct an SQL script to find the average salary in the Engineer table. [2]

``` SQL 
SELECT AVG(salary) AS 'avg_salary'
FROM engineer;
```

#### Question 2. State what a transaction is and identify four properties that define a transaction. [2]
A transaction is a sequence of SQL operations that are executed as a single unit of work in a database. The four properties that define a transaction is ACID, an acronyme for Atomicity, consistency, isolation and durability. 


#### Question 3. Identify three advantages of using views for a database. [3]
A view is a saved query that behaves like a table, it shows data form one or more tables. The advatages of using views include data abstraction, restricted user access, and reduced redundecy in queries. 

#### Question 4. Explain three data mining techniques. [6]


#### Question 5. Compare cloud and spatial databases. [4]


#### Question 6. Describe two features of distributed databases. [2]


#### Question 7. Identify and compare a NoSQL database with a relational database. [4]


#### Question 8. Explain the role of online analytical processing (OLAP) in business intelligence. [3]


#### Question 9. Explain the COMMIT transaction control language (TCL) command. [1]
The COMMIT command part of TCL or Transaction control language and saves all changes made to a table within a database. Once this operation is performed, the changes are permanent and visible to other users.