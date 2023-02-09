# ChatGPT Summary:

-   Referential Integrity:
    -   Default: NO ACTION
    -   CASCADE: updates/deletes referencing tuple
    -   SET NULL/SET DEFAULT: sets foreign key to NULL/default value
-   Integrity Constraints (ICs):
    -   Based on real world enterprise
    -   Checked but not inferred from instances

### Translating ISA to Relations

-   If not intuitive, don't set up

### Views

-   Definition stored instead of tuples
-   Can be dropped with DROP VIEW
-   DROP TABLE has options for handling views
-   Example: CREATE VIEW YoungActiveStudents(name,grade) AS SELECT S.name, E.grade FROM Students S, Enrolled E WHERE S.sid = E.sid and S.age<21

### Formal Relational Query Languages

-   Relational Algebra
    -   Boolean, integer operations
    -   Selection, Projection, Intersection, Join, Division, Renaming
    -   Union, Intersection, Difference with compatible schemas
    -   Equijoin (special case of condition join with equalities)
-   Relational Calculus
    -   Query applied to relation instances
    -   Result is also a relation instance
    -   Fixed schema for input relations and result

### Python

-   Access data using position notation or named fields
-----------------------------------------------------------------

# Lecture:

referential integrity in SQL:
- default is NO ACTION
- CASCADE updates to whatever it was or deletes it
- SET NULL/SET DEFAULT: sets foreign key value of referencing tuple

ICs are based upon the semantics of the real world enterprise that is being described
we can check a database instance to see if an IC is violated, but we can never infer an IC by looking at an instance

Translating ISA to Relations,
- if you cant intuitively set it up then don't set it up

Veiws
- view is just a relation, but we store a definition, rater than a set of tuples
- views can be dropped fusing the drop view command
	- how to handle drop table if theres a view on the tale?
	- DROP table commmand has options to le tthe usser specify this

CREATE VIEW YoungActiveStudents(name,grade)
	AS SELECT S.name, E.grade
	FROM Students S, Enrolled E
	WHERE S.sid = E.sid and S.age<21

formal relational query languages
relational algenbra
- boolean algebra - operands are logical values and have operations
- integer algebra, add sub mul neg and whatever
- Selection is circle, projection is pie, something something
- additional operations, intersection, join, division, renaming
- You can take the union of two sets, union compatible is correpsoning fields have the same type and sme number of fields
	- same with intersection and difference
	- can do a condition join i guess
	- equijoin, a special case of conditin join where the condition ccontains only equalities
relational calculus

A query is applied to relation instances, and the result of a query is also a relation instance.
- schemas of input relations for a query are fixed
- the schema for the result of a given query is also fixed, determined by definition of query langauge constructs

for getting stuff in python
- use position notation like in an array or  used named fields

