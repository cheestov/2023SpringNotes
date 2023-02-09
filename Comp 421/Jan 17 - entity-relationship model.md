# ChatGPT Summary:

-   Conceptual Design: the process of identifying entities and relationships in a system.
-   Entity: an object with a set of attributes, and an entity set is a collection of similar entities. Each set has a key and each attribute has a domain.
-   Relationships: an association among two or more entities, with a relationship set being a collection of similar relationships.
-   Aggregation: dividing entities into classes with ISA relationships, which are like subclasses, with overlap and covering constraints.
-   Entity vs Attribute: depends on the use and semantics of the data.
-   Entity vs Relationship: depends on the redundancy and misleading nature of the data.
-   Summary of Conceptual Design: follows requirement analysis, with the ER model being popular for conceptual design, and consisting of entities, relationships, and attributes.
-   Relational Database: a set of relations, with a relation consisting of an instance (a table with rows and columns) and a schema (specifying the relation name and the names and types of columns).
-   SELECT Statement: used to query a relational database and retrieve specific data.
-----------------------------------------------------------------

# Lecture

conceptual design: whwat are enttities and relationships?

Entity: an object distinguishable from other objects with a set of attributes
entity set: a collection of similar entities, 
- all entity sets have the same attributes
- each set has a key
- each attribute has a domain

Relationships: association among two or more entities
Relationship Set: Collection of similar relationships

Aggregation
- dividing entities into classes is smart I gguess
- if we declare A ISA B, every A entity is also a b entity,
- overlap constraints: can people be both A and B
- covering constraintsL does everyone have to be a or B
- ISA relationships are like subclasses

entity vs attribute:
shoulddepends upon the use we want to make of that info and the semantics of the data. If there are several addresses per employee then it should be an entity, or if the structure that contains all addresses is imporant then we should model addresses as an entity 

enetity vs relationship
- redundancyL dbudget stored for eacch dept managed by manager
- misleading: suggests dbudget associaited with other combinaiton

summary of conceptual design
- you follow requirement analysis
- er model popular for concept design
- entities, relationships, and attributes

Relational database: a set of relations
relation: Made up of 2 parts
- instance: a table, with rows and columbs
	- number of rows = cardinality,  number of fields = degree or arity
- schema: specifies namae of relation, plus a name and type for each ccolumn


SELECT s.name, E.cid
FROM Students S, Enrolled E
WHERE S.sid=E.sid and E.grade='A'



