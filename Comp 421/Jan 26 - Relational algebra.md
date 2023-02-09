# ChatGPT Summary:

### Division

-   Expresses queries to find sailors who have reserved all boats
-   Syntax: SELECT DISTICT Z.sno FROM A Z WHERE NOT EXISTS (SELECT B.pno FROM B2 B EXCEPT SELECT W.pno FROM A W WHERE Z.sno=W.sno)

### Except

-   Like a minus operator

### NATURAL JOIN

-   Joins two tables together with identical columns (e.g. both have an ID column with integers)
-   Joins all information for entries with the same values in the joined columns

### Find sailors who rented red boats

-   Syntax: WITH T1 AS (SELECT star FROM Boats WHERE Boats.color='red'), T2 AS (SELECT sid FROM Reserves NATURAL JOIN T1) SELECT DISTINCT sname FROM T2 NATURAL JOIN Sailors
-----------------------------------------------------------------
# Lecture:

Division
- useful for expressing queries like *find sailors who have reserved all boats*
- A/B, Grab everything in A taht has to do wiith B I think

A
SNO PNO

B2
PNO

SELECT DISTICT Z.sno
FROM A Z
WHERE NOT EXISTS (SELECT B.pno
                                FROM B2 B
                                EXCEPT
                                SELECT W.pno
                                FROM A W
                                WHERE Z.sno=W.sno)

^^^ Except will make it so only entries from left select are selected if they do not also exit in the right SELECT
So since the pnos are contained in both things, then nothing is collected and it means that the division operator is true for that entry or whatever

EXCEPT is like a minus

NATURAL JOIN joins two tables together where each table has to have an identical column, like both have an ID colum with an int. it then joins hte two tables with anything that has the same ID values and joins all of their info into single entries

To find all sailors who rented red boats

WITH T1 AS (SELECT star
                     FROM Boats
                     WHERE Boats.color='red'),
         T2 AS (SELECT sid
                     FROM Reserves
                     NATURAL JOIN T1)
SELECT DISTINCT sname
FROM T2
NATURAL JOIN Sailors


