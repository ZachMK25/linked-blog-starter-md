#### Logistics
- Closed book
- 70 minutes
- Calculator
- MC, short answer, SQL queries, and problem solving

## Typical DBMS Functionality
- Define a particular database in terms of its data types, structures, and constraints
- Construct or load the initial database contents on a secondary storage medium
- Manipulating the database
	- retrieval
	- modification
	- access
- Processing and sharing by a set of concurrent users; consistent and valid

- Queries: that access different parts of data and formulate results
- Transactions:

![[Example of a Simple Database]]


Self-describing nature of a database system:
- DBMS catalog stores the description of a particular database (data structures, types, constraints, etc.)

#### Schema vs State
- Schema changes very infrequently
	- Table definitions, data types, etc.
	- **intension**
	- name (of table) and attribute (column)
- State refers to the actual data in the database at a moment in time
	- **extension**
	- snapshot of the data
	- out of all of the possible values defined by the table constraints, this is a subset
	- ### Look out for discrete math symbols
		- ex: r(R) ⊂ dom (A1) x dom (A2) x ... x dom(An)
	- 

Tuple = Row
Relation = Table

**domain** = set of valid values for a given attribute; ex: integers

![[Screenshot 2025-03-25 at 9.40.53 AM.png]]

#### Relational Integrity Constraints
- **conditions** that must hold on **all** valid relation states
	- **Key** constraints, ex: unique
	- **Entity integrity** constraints
	- **Referential integrity**

#### SQL Datatypes
- Numeric
	- Integer numbers: INTEGER, INT, SMALLINT
	- FP (real) numbers: FLOAT, REAL, and DOUBLE PRECISION
	- ##### table bit/capacities for each on note sheet???
- Characters-string
	- Fixed-length: CHAR(n), CHARACTER(n)
	- Varying length: VARCHAR(n), CHAR VARYING(n), CHARCTER VARYING(n)
	- #### 1 byte/char assumption
- Bit-string datatypes
	- BIT(n)
	- BIT VARYING(n)
- Boolean data type
	- TRUE, FALSE, NULL
- DATE
- TIMESTAMP
- INTERVAL
- User-defined types
	- ex: CREATE DOMAIN SSN_TYPE AS CHAR(9);
### What to put on note sheet (DOUBLE SIDED)
- IO Cost for each algorithm
	- maybe the structure of each alg as well
- review in-class activities for SQL
- Homework as example of problem solving questions
- 