db_class
========
Q: Find the titles of all movies that have no ratings. 
select title
ans: from movie left outer join rating using (mID)
where  stars is null;

output: 
Star Wars
Titanic

Q: Some reviewers didn't provide a date with their rating. Find the names of all reviewers who have ratings with a NULL value for the date. 
select name
from reviewer natural join rating
where ratingDate is null;

output:
Chris Jackson
Daniel Lewis

Q:Write a query to return the ratings data in a more readable format: reviewer name, movie title, stars, and ratingDate. Also, sort the data, first by reviewer name, then by movie title, and lastly by number of stars. 
ans;
select name, title, stars, ratingDate
from (reviewer natural join rating) natural join movie
order by name, title, stars;

output:
Ashley White	E.T.	3	2011-01-02
Brittany Harris	Raiders of the Lost Ark	2	2011-01-30
Brittany Harris	Raiders of the Lost Ark	4	2011-01-12
Brittany Harris	The Sound of Music	2	2011-01-20
Chris Jackson	E.T.	2	2011-01-22
Chris Jackson	Raiders of the Lost Ark	4	<NULL>
Chris Jackson	The Sound of Music	3	2011-01-27
Daniel Lewis	Snow White	4	<NULL>
Elizabeth Thomas	Avatar	3	2011-01-15
Elizabeth Thomas	Snow White	5	2011-01-19
James Cameron	Avatar	5	2011-01-20
Mike Anderson	Gone with the Wind	3	2011-01-09
Sarah Martinez	Gone with the Wind	2	2011-01-22
Sarah Martinez	Gone with the Wind	4	2011-01-27

Q:
Find all years that have a movie that received a rating of 4 or 5, and sort them in increasing order. 
ans:
select distinct year
from rating natural join movie
where stars=4 or stars=5
order by year;
output:
1937
1939
1981
2009
