
Typical [[DBMS]] Functionality:
- Define a particular database in terms of its data types, structures, and constraints  
	- Construct or Load the initial database contents on a secondary storage medium
	- Manipulating the database:
	- Retrieval: Querying, generating reports
	- Modification: Insertions, deletions and updates to its content
	- Accessing the database through Web applications
	- Processing and Sharing by a set of concurrent users and application programs – yet, keeping all data valid and consistent

Applications interact with a [[database]] by generating:
- **Queries** that access different parts of [[data]] and formulate the result of a request
- **[[notes/SP25 SJSU/180B/Terms/Transaction]]** that may read some data and "update" certain values or generate new data and store that in the database

[[DBMS]] may additionally provide:
- Protection or security measures
- "Active" processing to take internal actions on data
- Presentation and visualization of data
- Maintenance of the database and associated programs over the lifetime of the applications

[[Example of a Simple Database]]

### Main Characteristics of the Database Approach

#### Self-describing nature of a database system: A DBMS catalog stores the description of a particular  
database (e.g. data structures, types, and constraints) 
- The description is called [[meta-data]]. 
- This allows the DBMS software to work with different database applications. 

#### Insulation between programs and data: 
- Called **program-data independence**. 
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

### Database Users  
#### Users may be divided into  
- Those who actually use and control the database content, and those who design, develop and maintain database applications (called “Actors on the Scene”), and  
- Those who design and develop the DBMS software and related tools, and the computer systems operators (called “Workers Behind the Scene”).
#### Actors on the scene  
**Database administrators**:  
- Responsible for authorizing access to the database, for coordinating and monitoring its use, acquiring software and hardware resources, controlling its use and monitoring efficiency of operations.  
**Database Designers**:
- Responsible to define the content, the structure, the constraints, and functions or transactions against the database. They must communicate with the end-users and understand their needs.

**End-users:** They use the data for queries, reports and some of them update the database content.  
- End-users can be categorized into:  
	- **Casual**: access database occasionally when needed  
	- **Naïve or Parametric**: they make up a large section of the end-user population. 
		- They use previously well-defined functions in the form of “canned transactions” against the database. 
		- Users of Mobile Apps mostly fall in this category 
		- Bank-tellers or reservation clerks are parametric users who do this activity for an entire shift of operations. 
		- Social Media Users post and read information from websites

	- **Sophisticated**:  
		- These include business analysts, scientists, engineers, others thoroughly familiar with the system capabilities.  
		- Many use tools in the form of software packages that work closely with the stored database.  
		- Stand-alone:  
			- Mostly maintain personal databases using ready-to-use packaged applications.
			- An example is the user of a tax program that creates its own internal database.  
			- Another example is a user that maintains a database of personal photos and videos.

System Analysts and Application Developers  
This category currently accounts for a very large proportion  
of the IT work force.  
◼ System Analysts: They understand the user  
requirements of naïve and sophisticated users and design  
applications including canned transactions to meet those  
requirements.  
◼ Application Programmers: Implement the  
specifications developed by analysts and test and debug  
them before deployment.  
◼ Business Analysts: There is an increasing need for  
such people who can analyze vast amounts of business  
data and real-time data (“Big Data”) for better decision  
making related to planning, advertising, marketing etc.


System Designers and Implementors: Design and  
implement DBMS packages in the form of modules and  
interfaces and test and debug them. The DBMS must interface  
with applications, language compilers, operating system  
components, etc.  
- Tool Developers: Design and implement software  
systems called tools for modeling and designing databases,  
performance monitoring, prototyping, test data generation,  
user interface creation, simulation etc. that facilitate building of  
applications and allow using database effectively.  
- Operators and Maintenance Personnel: They  
manage the actual running and maintenance of the database  
system hardware and software environment.

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
- when a DBMS may be unfeasible
	- Real-time requirements