When field values in a tuple are unknown or inapplicable, SQL makes them Null
- Nulll is complicated because it doesnt read as True or False for logical operators or equals. You need to treat it ike 3 values logic, always keeping in mind that a field could be null

IC Reveiw:
- Every legal instance of a relation must satisfy.
- can be used to ensure application sematntics or prevent inconsistencies
- Types of ICs:
	- Domains constraints
		- field values must be of right type. Always enforced
	- primary key constraints
	- foreign key constraints
	- general constraints

General constaints example:
CREATE TABLE Reserves 
(sname CHAR(10),
bid INTEGER.
day DATE,
PRIMARY KEY (bid,day),
CHECK ('Interlake' <>
				(SELECT B.bname
				FROM BOATS B
				WHERE B.bid=bid)))

or

for sailor rating do 
CHECK (rating>0 AND rating < 10)

TriggerL procedure that starts automatically if specified changes occur to the DBMS
- 3 parts: Event, Condition, Action

Example: Take note of new young sailors in a new table whenever they are created in the new sailors table

CREATE TRIGGER youngSailorUpdate
AFTER INSERT ON SAILORS
REFERENCING NEW TABLE NewSailors
FOR EACH STATEMENT
INSERT
INTO YoungSailors(sid, name, age, rating)
FROM NewSailors N
WHERE N.age <= 18