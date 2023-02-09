# Lecture:

GROUP BY and HAVING

Find the age of the youngest sailor for each rating level using i:
SELECT MIN (S.age)
FROM Sailors S
WHERE S.rating=i

Find the age of the youngest sailor using GROUP BY:
SELECT MIN (S.age)
FROM Sailors S
GROUP BY S.rating

- you can use more than one column to GROUP BY
- should generally use the primary key to GROUP BY

HAVING isused after GROUP BY and alows you to add a qaulification ot the group. Any tuple that does not qaulify will not be sorted into groups

For each red boat, find the number of reservations for this boat using HAVING:
SELECT B.bid, COUNT (star) scount
FROM Reserves R, Boats B
WHERE R.bid=B.bid
GROUP BY B.bid
HAVING B.color='red'

Find the age of the youngest sailor with age 18, for each rating with at least 2 such sailors:
SELECT S.rating, MIN(S.age) age
FROM Sailors S
WHERE S.age>=18
GROUP BY S.rating
HAVING COUNT(star)>1

Same thing but we use a subquery (worse) :
SELECT S.rating, MIN(S.age) minAge
FROM Sailors S
WHERE S.age>18
GROUP BY S.rating
HAVING 1<(SELECT COUNT(star)
					FROM Sailors S2
					WHERE S.rating=S2.rating AND S2.age>=18)

Aggregate operations like AVG or MIN cannot be nested!!

Find ratings for which the average age is the minimum over al ratings:
SELECT Temp.rating, Temp.avgage
FROM (SELECT S.rating, AVG(S.age) avgage
		FROM Sailors S
		GROUP BY S.rating) TEMP
WHERE TEMP.avgage=(SELECT MIN(Temp.avgage
									FROM Temp))




