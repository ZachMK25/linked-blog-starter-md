
### Main Characteristics of the Database Approach

#### Self-describing nature of a database system: A DBMS catalog stores the description of a particular  
database (e.g. data structures, types, and constraints) 
- The description is called [[meta-data]]. 
- This allows the DBMS software to work with different database applications. 

#### Insulation between programs and data: 
- Called **[[Program-Data Independence]]**. 
- Allows changing data structures and storage organization without having to change the DBMS access programs.  

* Note: Some newer systems such as a few NOSQL systems need no meta-data: they store the data definition within its structure making it self describing

#### Data Abstraction:  
- A data model is used to hide storage details and present the users with a conceptual view of the database.  
- Programs refer to the data model constructs rather than data storage details  
- Support of multiple views of the data: 
- Each user may see a different view of the database, which describes only the data of interest to that user.

#### Sharing of data and multi-user transaction processing: 
- Allowing a set of concurrent users to retrieve from and to update the database. 
- **Concurrency control** within the DBMS guarantees that each [[transaction]] is correctly executed or aborted  
- Recovery subsystem ensures each completed transaction has its effect permanently recorded in the database  
- **OLTP (Online Transaction Processing)** is a major part of database applications. This allows hundreds of concurrent transactions to execute per second.



### Advantages of Using the Database Approach
Controlling redundancy in data storage and in  
development and maintenance efforts.  
- Sharing of data among multiple users. 
- Restricting unauthorized access to data. Only the DBA staff uses privileged commands and  
facilities.  
- Providing persistent storage for program Objects 
	- E.g., Object-oriented DBMSs make program objects persistent– see Chapter 12.  
- Providing Storage Structures (e.g. indexes) for efficient Query Processing – see Chapter 17.

- Providing optimization of queries for efficient processing.  
- Providing backup and recovery services.  
- Providing multiple interfaces to different classes of users.  
- Representing complex relationships among data.  
- Enforcing integrity constraints on the database.  
- Drawing inferences and actions from the stored data using deductive and active rules and triggers.

- Potential for enforcing standards:  
	- This is very crucial for the success of database applications in large organizations. Standards refer to data item names, display formats, screens, report structures, meta-data (description of data), Web page layouts, etc.  
- Reduced application development time:  
	- Incremental time to add each new application is reduced.

- Flexibility to change data structures:  
	- Database structure may evolve as new requirements are defined.  
- Availability of current information:  
	- Extremely important for on-line transaction systems such as shopping, airline, hotel, car reservations.  
- Economies of scale:  
	- Wasteful overlap of resources and personnel can be avoided by consolidating data and applications across departments.

When not to use a DBMS
- Main costs
	- initial investment and hardware
	- overhead

- when a DBMS may be unnecessary
	- too little data
	- use a cache?

- when a DBMS may be unfeasible
	- Real-time requirements

