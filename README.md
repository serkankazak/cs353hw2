# cs353hw2

```
CS 353 HW 3

1.a:

 b | d | a | c | e | f
---+---+---+---+---+---
 1 | 1 | 1 | 2 | 4 | 7
 2 | 3 | 5 | 4 | 5 | 1
 2 | 4 | 4 | 5 | 3 | 3
 3 | 1 | 2 | 6 |   |
 3 | 2 | 3 | 8 | 4 | 4
 4 | 5 | 6 | 2 |   |

1.b:

 b | d | a | c | e | f
---+---+---+---+---+---
 1 | 1 | 1 | 2 | 4 | 7
 2 | 3 | 5 | 4 | 5 | 1
 2 | 4 | 4 | 5 | 3 | 3
 3 | 2 | 3 | 8 | 4 | 4
 3 | 8 |   |   | 2 | 2

1.c:

 b | d | a | c | e | f
---+---+---+---+---+---
 1 | 1 | 1 | 2 | 4 | 7
 2 | 3 | 5 | 4 | 5 | 1
 2 | 4 | 4 | 5 | 3 | 3
 3 | 1 | 2 | 6 |   |
 3 | 2 | 3 | 8 | 4 | 4
 3 | 8 |   |   | 2 | 2
 4 | 5 | 6 | 2 |   |

1.d:

 a | b | c | d | b | d | e | f
---+---+---+---+---+---+---+---
 1 | 1 | 2 | 1 | 3 | 8 | 2 | 2
 2 | 3 | 6 | 1 |   |   |   |
 3 | 3 | 8 | 2 |   |   |   |
 4 | 2 | 5 | 4 |   |   |   |
 5 | 2 | 4 | 3 |   |   |   |
 6 | 4 | 2 | 5 | 3 | 8 | 2 | 2
   |   |   |   | 2 | 3 | 5 | 1
   |   |   |   | 3 | 2 | 4 | 4
   |   |   |   | 1 | 1 | 4 | 7
   |   |   |   | 2 | 4 | 3 | 3

2.a:

select studentId from Student s except select s.studentId from Student s, Pokemon p, Caught c where s.studentId = c.StudentId and p.pokemonId = c.pokemonId and p.category = "water"

2.b:

select p.pokemonId from Student s, Pokemon p, Caught c where s.studentId = c.StudentId and p.pokemonId = c.pokemonId and p.category != "fire" and c.location = "ea" group by p.pokemonName order by count(s.studentId) desc limit 1

2.c:

select s.studentId from Student s, Pokemon p, Caught c where s.studentId = c.StudentId and p.pokemonId = c.pokemonId group by s.studentId having count(distinct p.pokemonName) = (select count(*) from Pokemon)

2.d:

create view ea_pop as (select p.pokemonName, p.category from Student s, Pokemon p, Caught c where s.studentId = c.StudentId and p.pokemonId = c.pokemonId and c.location = "ea" group by p.pokemonName having count(s.studentId) > 10)
```
