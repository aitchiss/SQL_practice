# SQL Homework

The Dominion Cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'
```
# terminal
createdb marvel 
```

Next, run the provided SQL script to populate your database:
```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

command: SELECT * FROM movies;

result: 
id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 21:00
  2 | The Incredible Hulk                 | 2008 | 14:20
  3 | Iron Man 2                          | 2010 | 18:45
  4 | Thor                                | 2011 | 22:20
  5 | Captain America: The First Avenger  | 2011 | 16:45
  6 | Avengers Assemble                   | 2012 | 21:05
  7 | Iron Man 3                          | 2013 | 17:30
  8 | Thor: The Dark World                | 2013 | 14:30
  9 | Batman Begins                       | 2005 | 20:00
 10 | Captain America: The Winter Soldier | 2014 | 23:25
 11 | Guardians of the Galaxy             | 2014 | 17:40
 12 | Avengers: Age of Ultron             | 2015 | 23:40
 13 | Ant-Man                             | 2015 | 16:35
 14 | Captain America: Civil War          | 2016 | 23:40
 15 | Doctor Strange                      | 2016 | 23:30

2. Return ONLY the name column from the 'people' table

command: SELECT name FROM people;

result: 
       name        
--------------------
 Adam  Baxter
 Alice Loudon
 Chris Brown
 Colin Farquhar
 David  Hale
 Douglas Crooke
 Ewen Carr
 Ferdinando Sendyka
 Craig Morton
 Andrew
 Andrew
 Graeme Bell
 Josef Meszaros
 Km North
 Leon-Paul Hart
 Lewis Brown
 Richard Page Croft
 Rob Flett
 Robert Ball
 Robert Brice
 Ross Crichton
 Simon Smith
 Suzanne Aitchison


3.Oops! Someone at CodeClan spelled Kim's name wrong! Change it to reflect the proper spelling (change 'Km North' to 'Kim North').

command: UPDATE people SET name = 'Kim North' WHERE name = 'Km North';

result: SELECT name FROM people; now shows entry as 'Kim North'

4. Return ONLY your name from the 'people' table.

command: SELECT name FROM people WHERE name = 'Suzanne Aitchison';

result: 
       name        
-------------------
 Suzanne Aitchison

5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

command: DELETE FROM movies WHERE id = 9;

result: SELECT * FROM movies; now shows Batman Begins is missing

6. Create a new entry in the 'people' table with the name of one of the instructors.

command: INSERT INTO people (name) VALUES ('Keith Douglas');

result: SELECT * FROM people; now shows Keith as last entry

7. Craig Morton, has decided to hijack our movie evening, Remove him from the table of people.

command: DELETE FROM people WHERE name = 'Craig Morton';

result: SELECT * FROM people; now shows no entry for Craig

8. Somehow the list of people includes two people named 'Andrew'. Change these entries to the proper names ('Jeff 4', 'Jeff 5')

command: UPDATE people SET name = 'Jeff 4' WHERE id=10;
command: UPDATE people SET name='Jeff 5' WHERE id=11;

result: SELECT * FROM people; shows Jeff 4 and Jeff 5, with same id numbers:

10 | Jeff 4
11 | Jeff 5

9. The cinema has just heard that they will be holding an exclusive midnight showing of 'Guardians of the Galaxy 2'!! Create a new entry in the 'movies' table to reflect this.
10. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 12:10 to 21:30

## Extension

1. Research how to delete multiple entries from your table in a single command.
