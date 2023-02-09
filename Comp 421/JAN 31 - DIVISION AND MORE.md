# Lecture:

SELECT DISTINCT Z.sid
FROM Reserves as Z
WHERE NOT EXISTS ( SELECT Y.bid
                                  FROM Boats Y
                                   EXCEPT
                                   SELECT W.bid
                                   FROM Reserves W
                                   WHERE W.sid=Z.sid)

THIS IS HOW YOU DO DIVIVSION DONT FORGET


SELECT [DISTINCT] Target-ist
FROM elation-list
WHERE Qualification


This is a complicated way to group things and order them 
SELECT T.name,
ROW_NUMBER() OVER(PARTITION BY T.games_played ORDER BY T.name ASC)
FROM Teams T, Conferences C
WHERE C.conference_id=T.conference_id AND C.short_name='{conf_name}'


Take note of order by thing
SELECT COUNT(name)
Selects the count of that row in the thing
RANK() does almost the same thing as row number except it gives them the same number for each group instead of different numbers