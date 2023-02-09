# ChatGPT summary:
*-   Database: a collection of related and queryable data modeled after real-world enterprise entities and relationships, managed by a DBMS software
-   *Files vs Database: a database offers better handling of large datasets, different queries, protection from data inconsistencies, crash recovery, and security and access control compared to a normal file.*
-   *Data Model: a collection of concepts that relate to data, with the most widely used being the relational model. Relations are tables with rows and columns, and every relation has a schema that describes its fields.*
-    *Levels of Abstraction: multiple views for different users implementing security and concurrency protection
-   *Schemas: defined using a data definition language and data is modified using a data management language, resulting in data independence
-   *Concurrent Users: handled using locks and transactions ensure atomicity
-   *Write Ahead Log (WAL) Protocol: used to keep a log of all actions carried out by the DBMS while executing a set of transactions, and to recover the database after a crash. recover the database after a crash.

-----------------------------------------------------------------
# LECTURE
database - a large collection of related and queryable bits
- it models real world enterprise, entities and relationships
- a database management system (DBMS) is a software package designed to store and manage databases

files v db:
- application must stage large datasets between main meory and secondary storage
- special code for different queries
- must protect data from inconsistencies from concurrent users
- crash recovery
- security and access control 
^ Cant do all of these in a normal file ^

data model: collection of concepts relating data 
A relational model of data is most widely used
relation: a table with rows and columns
every relation has a schema, which describes the allowed contents of comuns, or fields

levvels of abstraction, with many veiws for diffferent users implementing security and concurrence protection

conceptual schema (logical structure) and physical schema (files and indexes used)

schemas are defines useing a data definition language
data is modified by a data management langauge

data independence, application insulated from how data is actually structured and stored

Concurrent users are done using locks. if one person needs to write to something that another person needs to read, the database locks it for someone and then the other person waits

ensure atmoicity, even if system crashes in the middle of a thing, then we dont lose everything.
keep a log of all actions carried out by the DBMS while executing a set of Xacts,
- before a change is made to the database, teh corresponding log entry is forced to a safe locaiton, a Write ahead log, WAL protocol
- after the crash, teh effects  of partially executed transaction are undone using the log

The following actions are recorded in hte log, on a write we save values and on other things we saveo thers



