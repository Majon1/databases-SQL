####Exercise 1-20

1. SELECT name FROM movies;
2. SELECT name, year FROM movies;
3. SELECT name FROM movies WHERE year = 1940;
4. SELECT name FROM movies WHERE year < 1950;
5. SELECT name FROM movies WHERE year >= 1940 AND year <= 1950;
6. SELECT name FROM movies WHERE year < 1950 OR year > 1980;
7. SELECT name FROM movies WHERE year < 1940 OR year > 1940;
8. SELECT name FROM movies ORDER BY name; 
9. SELECT name FROM movies ORDER BY name DESC;
10. SELECT name, year FROM movies ORDER BY year DESC, name;
11. SELECT DISTINCT forename FROM names;
12. SELECT DISTINCT forename, surname FROM names;
13. SELECT COUNT(*) FROM employees;
14. SELECT COUNT(*) FROM employees WHERE salary > 2000;
15. SELECT SUM(salary) FROM employees;
16. SELECT MAX(salary) FROM employees;
17. SELECT COUNT(DISTINCT company) FROM employees;
18. SELECT company, COUNT(name) AS total FROM employees GROUP BY company ORDER BY total;
19. SELECT company, MAX(salary) AS total FROM employees GROUP BY company ORDER BY name;
20. SELECT company, MAX(salary) AS total FROM employees WHERE salary >= 5000 GROUP BY company;

####Exercise 21-40

21. SELECT name, score FROM Players, Results WHERE Results.player_id = Players.id;
22. SELECT name, score FROM Players, Results WHERE Results.player_id = Players.id AND Players.name = 'Uolevi';
23. SELECT name, score FROM Players, Results WHERE Results.player_id = Players.id AND Results.score > 250;
24. SELECT name, score FROM Players, Results WHERE Results.player_id = Players.id ORDER BY Results.score DESC, name;
25. SELECT name, MAX(score) FROM Players, Results WHERE Results.player_id = Players.id GROUP BY Players.id;
26. SELECT name, COUNT(score) FROM Players, Results WHERE Results.player_id = Players.id GROUP BY Players.id;
27. SELECT S.name, C.name, G.grade FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id;
28. SELECT C.name, G.grade FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id AND S.name = 'Uolevi';
29. SELECT S.name, G.grade FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id AND C.name = 'Basic Coding';
30. SELECT S.name, C.name, G.grade FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id AND G.grade >= 4;
31. SELECT S.name, COUNT(C.id) FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id GROUP BY S.id;
32. SELECT S.name, MAX(G.grade) FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id GROUP BY S.id;
33. SELECT C.name, D.name FROM Cities C, Cities D, Flights F WHERE C.id = F.departure_id AND D.id = F.destination_id;
34. SELECT D.name FROM Cities C, Cities D, Flights F WHERE C.id = F.departure_id AND D.id = F.destination_id AND C.name = 'Helsinki';
35. SELECT name, COUNT(score) FROM Players LEFT JOIN Results ON Results.player_id = Players.id GROUP BY Players.id;
36. SELECT S.name, COUNT(G.grade) FROM Students S, Courses C LEFT JOIN Gradings G ON S.id = G.student_id AND C.id = G.course_id GROUP BY S.id;
37. SELECT C.name, COUNT(G.grade) FROM Students S, Courses C LEFT JOIN Gradings G ON S.id = G.student_id AND C.id = G.course_id GROUP BY C.id;
38. SELECT C.name FROM Students S, Courses C, Gradings G WHERE S.id = G.student_id AND C.id = G.course_id GROUP BY C.id;
39. SELECT C.name FROM Courses C LEFT JOIN Gradings G ON G.course_id = C.id WHERE G.course_id IS NULL GROUP BY C.name; 
40. SELECT C.name, COUNT(F.departure_id) FROM Cities C, Cities D LEFT JOIN Flights F ON C.id = F.departure_id AND D.id = F.destination_id GROUP BY C.id;

####Exercise 41-60

41. SELECT name, price*2 FROM Products;
42. SELECT name, price FROM Products WHERE price % 2 = 0;
43. SELECT word, LENGTH(word) FROM Words;
44. SELECT word FROM Words WHERE LENGTH(word) < 6;
45. SELECT word FROM Words ORDER BY LENGTH(word), word;
46. SELECT forename || " " || surname FROM Users;
47. SELECT SUM(LENGTH(word)) FROM Words;
48. SELECT product, (price * amount) FROM Orders;
49. SELECT SUM(price * amount) FROM Orders;
50. SELECT name FROM Movies WHERE (year % 4 = 0 AND year % 100 <> 0) OR year % 400 = 0;
51. SELECT name FROM Products WHERE price =(SELECT MIN(price) FROM Products);
52. SELECT name FROM Products WHERE price <= 2 * (SELECT MIN(price) FROM Products);
53. SELECT name FROM Products WHERE price IN (SELECT price FROM Products GROUP BY price HAVING COUNT(*)=1) GROUP BY name;
54. SELECT word FROM Words ORDER BY word LIMIT 1;
55. SELECT word FROM Words ORDER BY word LIMIT 1 OFFSET 1;
56. SELECT word FROM Words ORDER BY word LIMIT -1 OFFSET 1;
57. SELECT word FROM Words WHERE word LIKE '%i%';
58. SELECT word FROM Words WHERE word LIKE 'a%' GROUP BY word;   
59. SELECT word FROM Words WHERE word LIKE '_p%' AND LENGTH(word) = 5;
60. SELECT word FROM Words WHERE word LIKE '%a%a%' AND word NOT LIKE '%a%a%a%';