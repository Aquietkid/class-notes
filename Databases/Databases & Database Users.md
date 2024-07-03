# Types of Databases

- multimedia databases: images and audio/video streams
- Geographic information systems (GISs): maps, weather data, and satellite images
- Data warehouses/online analytical processing (OLAP): extract important business data from large databases
- Real-time (Active database technology): used in industrial and manufacturing processes

# Introduction to Databases

**Database** is a collection of related data. **Data** are facts that can be recorded and have an implicit meaning. However, this definition leads to ambiguity in what a database actually is. There are some properties of databases:

- A database represents a part of the world, called the _miniworld_ or the _universe of discourse_. Changes in the miniworld are reflected in the database too.
- The data in a database is logically coherent with an inherent meaning. It is not a random data collection.
- Databases are designed, built, and populated with data for a specific purpose and have a set of intended users.

Data which describes a database record is the **meta-data**. This includes data types, field sizes, allowable values, and documentation.

# Database Management Systems (DBMS)

A database management system (DBMS) is a program for _defining_, _constructing_, _manipulating_, and _sharing_ a database. _Defining_ involves specifying the nature of the data: datatype, structure, and constraints of the data. _Constructing_ a database involves storing the data on a physical medium. _Manipulation_ allows us to retrieve and update data, update the database structure, and analyze the data. _Sharing_ allows multiple users and applications to access the database simultaneously.

Databases can be accessed by applications using _queries_ (which retrieve data) or _transactions_ (which retrieve and/or update data) in a database. A DBMS also helps **protect** the database by offering _system protection_ (against hardware and software malfunctions) and _security protection_ (which prevents unauthorized access), and **maintain** the database to incorporate changes as they take place in the real world. A database combined with a DBMS is referred to as a database system. Most databases have various kinds of _records_ and many _relationships_ among the data.

# Database Development Lifecycle

![[Database Development Lifecycle (DDLC).png]]

1. Requirements specification & analysis: analyze the feasibility and other characteristics of the specified requirements.
2. Conceptual Design: build an ER model
3. Logical Design: convert the ER model into the relational model
4. Physical Design: construct the database and its tables, and populate them with data.

# Characteristics of the Database Approach

File processing requires each “department” using the software to maintain separate files which contain relevant details. However, this adds some redundancy to the data since there has to be at least one common factor on the basis of which entries in a file can be related to those in another. Moreover, file management systems require separate read/write methods for each department.

Following are some characteristics of database systems which separate them from standard file management:

1. Self-describing nature of a database system: each database has its own database catalog which stores the meta-data of the database. This helps the DBMS and other applications to interact with the database instead of requiring specific application code for reading files.
2. Insulation between programs and data, and data abstraction: DBMSs do not require changes to the program structure when the database structure is changed. Any changes to the database structure are stored in the catalog and does not require that the access program be modified as per the changes. This is **program-data independence**. And _operation_ separates the interface and the implementation of data access. This is called **program-operations independence**.
3. Support of multiple views of the data:
4. Sharing of data and multiuser transaction processing

# Advantages of DBMS Systems

1. **Redundancy**: repetition in files wastes storage space, requires changes be made in each file, and data may become inconsistent. Databases promote _data normalization_, i.e., each logical data item be defined only at one place in the database. In practice, however, data might be redundantly stored for improved performance. However, this is desirable and is controlled - hence called _controlled redundancy_. This is also known as _denormalization_.
2. **Restricting Unauthorized Access**: Each DBMS has a _security and authorization subsystem._ The database administrator (DBA) can create accounts for access to these databases.
3. **Providing Persistent Storage for Program Objects**: Data from objects and object-oriented data structures, when stored in files, loses the structure it had in the program. However, databases maintain this structure and the DBMS handles any relevant conversions.
4. **Providing Storage Structures and Search Techniques for Efficient Query Processing**: Search queries are stored in indexes as trees or hash tables. The DBMS has a _buffering_ or _caching_ module which maintains parts of the database in the main memory.
5. **Providing Backup and Recovery**: This system ensures that the database can recover from any hardware and software failures.
6. **Providing Multiple User Interfaces**: DBMSs provide various interfaces like programming language interfaces, query languages, mobile clients, and GUIs to address the needs of different users.
7. **Representing Complex Relationships Among Data**: A DBMS must be able to represent complex relationships, query data for these relationships, and incorporate the changes to these relationships as they occur in the miniworld.
8. **Forcing Integrity Constraints**: The database specifies the datatype of the data to be stored, and constraints like the length.
9. **Permitting Inferencing and Actions Using Triggers**: A trigger is a rule which performs some additional operations when actions are performed on the database. More involved procedures are called stored procedures. Active database systems can execute certain statements automatically.
10. More advantages involve reduced development times, flexibility, better standard enforcements, and availability of up-to-date data. The centralized storage and processing of data allows investing in high-performance, global-level hardware instead of lower-performance localized machines.