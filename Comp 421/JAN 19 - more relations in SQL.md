# ChatGPT Summary

Summary of SQL Notes:

-   DROP TABLE deletes a table and its schema.
-   ALTER TABLE adds a new field to the schema of a table.
-   DELETE FROM deletes all tuples satisfying some condition.

Relational Model Summary:

-   Integrity Constraints: conditions that must be true for any instance of a database.
-   Primary Key Constraint: no two tuples can have the same values in all key fields of a relation.
-   Candidate Keys: one of which is chosen as a primary key.
-   Foreign Key: a set of fields in one relation that references a tuple in another relation.

SQL Commands:

-   CREATE TABLE creates a table with specified columns, primary key, and foreign key.
-   PRIMARY KEY specifies a primary key for the relation.
-   FOREIGN KEY specifies a foreign key for the relation.
-   ON DELETE CASCADE and ON UPDATE CASCADE specify how the foreign key is affected when the referenced tuple is deleted or updated.
-----------------------------------------------------------------

# LECTURE:

Creating relations in SQL

DROP TABLE Students 
- deletes the students table and the schema aand everything

ALTER TABLE SUTDENTS ADD COLUMN firstYear integer
the schema of students is altered by adding a new field, every tuple in hte current instance is extended with a null vlaue in the new field 

can delete all tupels satisfying some condition
DELETE FROM Students S
WHERE S.name = 'Smith'

Relational lmodel summary: stuff

Integrity Constraints
- IC: condition that must be true for any instance of database: domain constraints
	- are specified when schema is defined
	- checed when relations are modified
- a legal instance of a relation satisfies all specified ICs
	- DBMS should not allow illegal instannces
- if dbms checs ICs stored data is more faithful to real world meaning 

Primary key constraint, for a relation if : no two tuples can have the same values in all key fields
this is not true for any subset of the key
- if the key is overspecified, then superkey
- if more than one key for a relation, one chosen by dba as the primary 
- key

Cadidate keys (specified using UNIQUE), one of which is chosen as a primary key

foreign key set of fields in one relation that is used to reference a typle in another relation, must be the primary key of the second relation


CREATE TABLE Enrolled
	(sid CHAR(20), cid CHAR(20), grade CHAR(2),
		PRIMARY KEY (SID,CID),
		FOREIGN KEY (sid)
			REFERENCES STUDENTS
			ON DELETE CASCADE
			ON UPDATE CASCADE
			);