# SQL Tutorial

## SELECT from Nobel Tutorial

Practicing simple SQL queries on a single table.

This tutorial is concerned with a table of Nobel prize winners:

nobel(yr, subject, winner)
Using the SELECT statement.

1. Winners from 1950

SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
 
2. Show who won the 1962 prize for Literature.

SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
  
3. Show the year and subject that won 'Albert Einstein' his prize.

SELECT yr, subject
  FROM nobel
 WHERE winner = 'Albert Einstein'
   
4. Give the name of the 'Peace' winners since the year 2000, including 2000.

SELECT winner
  FROM nobel
 WHERE subject = 'Peace' AND yr >= 2000
 
5. Show all details (yr, subject, winner) of the Literature prize winners for 1980 to 1989 inclusive.

SELECT *
  FROM nobel
 WHERE subject = 'Literature' AND yr BETWEEN 1980 AND 1989
 
6. Show all details of the presidential winners: Theodore Roosevelt, Woodrow Wilson, Jimmy Carter, Barack Obama

SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt',
'Woodrow Wilson',
'Jimmy Carter',
'Barack Obama')

7. Show the winners with first name John

SELECT winner FROM nobel
 WHERE winner like 'John%'
 
8. Show the year, subject, and name of Physics winners for 1980 together with the Chemistry winners for 1984.

select * 
from nobel 
where (yr=1980 and subject='physics') or (yr=1984 and subject='chemistry');

9. Show the year, subject, and name of winners for 1980 excluding Chemistry and Medicine

SELECT *
FROM nobel
WHERE yr=1980 AND
  subject NOT IN ('Chemistry','Medicine')

10. Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)

SELECT *
FROM nobel
WHERE (yr < 1910 AND subject = 'Medicine') or ( yr >= 2004 AND subject = 'Literature')

11. Find all details of the prize won by PETER GRÜNBERG

SELECT *
FROM nobel
WHERE winner LIKE 'PETER GRÜNBERG'

12. Find all details of the prize won by EUGENE O'NEILL

SELECT *
FROM nobel
WHERE winner LIKE 'EUGENE O\'NEILL'

13. List the winners, year and subject where the winner starts with Sir. Show the the most recent first, then by name order.
