Left Join returns every tuple for the left table, puts null for entries that dont match with the right one at all
- Null matches to None in python

FULLL OUTER JOIN returns all rows from all tables with the specificied attributes joined or null if there is no match
Select bid 
from boats b
FULL OUTER JOIN Reserves ON R.bid=b.bid