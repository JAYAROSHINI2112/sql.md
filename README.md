#### Create the following table with the following values.

Database Name : `sqlpractice`

Table Name : `Student`

##### _Student_ Table

        | Roll | Sname   | Gender | Dob        | Total | Average | Grade |
        | ---- | ------- | ------ | ---------- | ----- | ------- | ----- |
        | 1    | Anand   | M      | 05/13/2001 | 407   | 81.4    | B     |
        | 2    | Ajay    | M      | 04/02/2001 | 400   | 80      | C     |
        | 3    | Bharath | M      | 11/05/2000 | 355   | 71      | D     |
        | 4    | Shivani | F      | 05/06/2001 | 476   | 95.2    | A     |
        | 5    | Sarchin | M      | 12/23/2001 | 400   | 80      | C     |
        | 6    | Dhoni   | M      | 11/17/2000 | 415   | 83      | B     |
        | 7    | Kamala  | F      | 12/05/2001 | 400   | 80      | C     |
        | 8    | Varun   | M      | 11/11/2000 | 470   | 94      | A     |
        | 9    | Rekha   | F      | 10/15/2000 | 490   | 98      | A     | 
        
##### _Personal_ Table

        | Roll | Parent | Address          | Phone_No |
        | ---- | ------ | ---------------- | -------- |
        | 2    | ABC    | 1st Cross Street | 12345678 |
        | 3    | XYZ    | 2nd Cross Street | 41234561 |
        | 4    | PQR    | 3rd Cross Street | 12370171 |
        | 7    | LMN    | 4th Cross Street | 40007714 |
        | 9    | ABCD   | 5th Cross Street | 56789101 |
        
#### Q01. Display name and gender of all the students.
**Answer**

>*Query*
```sql
    SELECT Sname, Gender
    FROM Student;
```
>*Output*
```
+---------+--------+
|  Sname  | Gender |
+---------+--------+
| Anand   | M      |
| Ajay    | M      |
| Bharath | M      |
| Shivani | F      |
| Sarchin | M      |
| Dhoni   | M      |
| Kamala  | F      |
| Varun   | M      |
| Rekha   | F      |
+---------+--------+
```
#### Q02. Display the contents of the entire table.
**Answer**

>*Query*
```sql
SELECT * FROM Student;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   400 |   80.00 | C     |
|    6 | Dhoni   | M      | 2001-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-11 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q03. Display the unique values of `Total` from the table.
**Answer**

>*Query*
```sql
SELECT distinct Total FROM Student;
```
>*Output*
```
+-------+
| Total |
+-------+
|   407 |
|   355 |
|   476 |
|   400 |
|   415 |
|   470 |
|   490 |
+-------+
```
#### Q04. Display roll number and name of the male students.
**Answer**

>*Query*
```sql
SELECT Roll,Sname FROM Student WHERE Gender='M';
```
>*Output*
```
+------+---------+
| Roll | Sname   |
+------+---------+
|    1 | Anand   |
|    2 | Ajay    |
|    3 | Bharath |
|    5 | Sarchin |
|    6 | Dhoni   |
|    8 | Varun   |
+------+---------+
```
#### Q05. Display the roll number and name of male students who have scored above 400.
**Answer**

>*Query*
```sql
SELECT Roll,Sname FROM Student WHERE Total>400 AND Gender='M';
```
>*Output*
```
+------+-------+
| Roll | Sname |
+------+-------+
|    1 | Anand |
|    6 | Dhoni |
|    8 | Varun |
+------+-------+
```
#### Q06. Display the details of students who have scored between 400 and 450. (Limits inclusive)
**Answer**

>*Query*
```sql
SELECT * FROM Student WHERE Total BETWEEN >=400 AND <=450
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    5 | Sarchin | M      | 2001-12-23 |   400 |   80.00 | C     |
|    6 | Dhoni   | M      | 2001-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q07. Display details of male students who have scored between 400 and 450.
**Answer**

>*Query*
```sql
SELECT * FROM Student WHERE Gender='M' AND Total BETWEEN >=400 AND <=450
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-02-04 |   400 |   80.00 | C     |
|    5 | Sarchin | M      | 2001-12-23 |   400 |   80.00 | C     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q08. Display names of students who have scored the grades A, B or C from the table.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE Grade='A' OR Grade='B' OR Grade='C';
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Anand   |
| Ajay    |
| Shivani |
| Sarchin |
| Dhoni   |
| Kamala  |
| Varun   |
| Rekha   |
+---------+
```
#### Q09. Display the name of female students who have scored the grades A or B.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE Gender='F' AND Grade='A' OR Gender='F' AND Grade='B';
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Shivani |
| Rekha   |
+---------+
```
#### Q10. Display the roll numbers of students who have scored grade other than A or B.
**Answer**

>*Query*
```sql
SELECT Roll FROM Student WHERE NOT Grade='A' AND NOT Grade='B';
```
>*Output*
```
+------+
| Roll |
+------+
|    2 |
|    3 |
|    5 |
|    7 |
+------+
```
#### Q11. Display the names of the students born in the year 2001.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE YEAR(Dob)='2001';
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Anand   |
| Ajay    |
| Shivani |
| Sarchin |
| Kamala  |
+---------+
```
#### Q12. Display the names of the students born in the month of November 2000.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE MONTH(Dob)='11' AND YEAR(Dob)='2000';
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Bharath |
| Dhoni   |
| Varun   |
+---------+
```
#### Q13. Display the names of the students born in the year 2000 but not in the month of November.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE  NOT MONTH(Dob)='11' AND YEAR(Dob)='2000';
```
>*Output*
```
+-------+
| Sname |
+-------+
| Rekha |
+-------+
```
#### Q14. Display the different grades obtained by the students.
**Answer**

>*Query*
```sql
SELECT distinct Grade FROM Student;
```
>*Output*
```
+-------+
| Grade |
+-------+
| B     |
| C     |
| D     |
| A     |
+-------+
```
#### Q15. Display the name, average and grade of all female students in the following format:
`Shivani has scored an average of 95.2 with grade A.`

**Answer**

>*Query*
```sql
SELECT concat(Sname, ' has scored an average of ', Average, ' with grade ', Grade,'.') as Female Details FROM Student WHERE Gender='F';
```
>*Output*
```
+------------------------------------------------------+
|  Female Details                                      |
+------------------------------------------------------+
| Shivani has scored an average of 95.20 with grade A. |
| Kamala has scored an average of 80.00 with grade C.  |
| Rekha has scored an average of 98.00 with grade A.   |
+------------------------------------------------------+
```
#### Q16. Assume there is no average column in the table and the Total attribute is the expression of 5 subjects mark. Display the name and average marks of all the female students.
**Answer**

>*Query*
```sql
SELECT Sname , Total/5 AS Avg FROM Student WHERE Gender='F'
```
>*Output*
```
+---------+---------+
| Sname   | Avg     |
+---------+---------+
| Shivani | 95.2000 |
| Kamala  | 80.0000 |
| Rekha   | 98.0000 |
+---------+---------+
```
#### Q17. Display names of students whose name starts with 'A'.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE Sname LIKE 'A%';
```
>*Output*
```
+-------+
| Sname |
+-------+
| Anand |
| Ajay  |
+-------+
```
#### Q18. Display the roll number, name, total of the students whose starts with 'A' and ends with 'd'.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE Sname LIKE ('A%') and ENAME LIKE('%d');
```
>*Output*
```
+------+-------+-------+
| Roll | Sname | Total |
+------+-------+-------+
|    1 | Anand |   407 |
+------+-------+-------+
```
#### Q19. Display the details of students whose name is exactly 5 charcters in length.
**Answer**

>*Query*
```sql
SELECT * FROM Student WHERE Sname LENGTH(Sname)='5'; 
```
>*Output*
```
+------+-------+--------+------------+-------+---------+-------+
| Roll | Sname | Gender | Dob        | Total | Average | Grade |
+------+-------+--------+------------+-------+---------+-------+
|    1 | Anand | M      | 2001-05-13 |   407 |   81.40 | B     |
|    6 | Dhoni | M      | 2000-11-17 |   415 |   83.00 | B     |
|    8 | Varun | M      | 2000-11-11 |   470 |   94.00 | A     |
|    9 | Rekha | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+-------+--------+------------+-------+---------+-------+
```
#### Q20. Display the details of students whose name has 'i'.
**Answer**

>*Query*
```sql
SELECT * FROM Student WHERE Sname LIKE '%i%'; 
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   400 |   80.00 | C     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q21. Display the names of students not starting with A or S.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE Sname NOT LIKE ('A%') and Sname NOT LIKE('S%');
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Bharath |
| Dhoni   |
| Kamala  |
| Varun   |
| Rekha   |
+---------+
```
#### Q22. Display names of students whose birth date is 5.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student WHERE DAY(Dob)='05';
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Bharath |
| Kamala  |
+---------+
```
#### Q23. Display the names of students in the table in alphabetical order.
**Answer**

>*Query*
```sql
SELECT Sname FROM Student ORDER BY Sname ASC;
```
>*Output*
```
+---------+
| Sname   |
+---------+
| Ajay    |
| Anand   |
| Bharath |
| Dhoni   |
| Kamala  |
| Rekha   |
| Sarchin |
| Shivani |
| Varun   |
+---------+
```
#### Q24. Display the name and total of female students in descending order of total.
**Answer**

>*Query*
```sql
SELECT Sname,Total FROM Student WHERE Gender='F' ORDER BY Total DESC ;
```
>*Output*
```
+---------+-------+
| Sname   | Total |
+---------+-------+
| Rekha   |   490 |
| Shivani |   476 |
| Kamala  |   400 |
+---------+-------+
```
#### Q25. Display the name, grade and total of all the students who have scored above 395 in descending order of their grades and ascending order of their name.
**Answer**

>*Query*
```sql
SELECT Sname,Grade,Total FROM Student WHERE Total>395 ORDER BY Grade DESC,Sname ASC;
```
>*Output*
```
+---------+-------+-------+
| Sname   | Grade | Total |
+---------+-------+-------+
| Ajay    | C     |   400 |
| Kamala  | C     |   400 |
| Sarchin | C     |   400 |
| Anand   | B     |   407 |
| Dhoni   | B     |   415 |
| Rekha   | A     |   490 |
| Shivani | A     |   476 |
| Varun   | A     |   470 |
+---------+-------+-------+
```
#### Q26. Find the sum of the total marks obtained by students who have scored the grade 'A'.
**Answer**

>*Query*
```sql
SELECT SUM(Total) FROM Student WHERE Grade='A';
```
>*Output*
```
+------------+
| SUM(Total) |
+------------+
|       1436 |
+------------+
```
#### Q27. Display the average of the average marks scored by 'A' graders.
**Answer**

>*Query*
```sql
SELECT AVG(Average) FROM Student WHERE Grade='A';
```
>*Output*
```
+------------+
|AVG(Average)|
+------------+
|  95.673333 |
+------------+
```
#### Q28. Display the total number of students in the table.
**Answer**

>*Query*
```sql
SELECT COUNT(Roll) FROM Student;
```
>*Output*
```
+--------------+
| COUNT(Roll) |
+--------------+
|            9 |
+--------------+
```
#### Q29. Display the number of different grades available in the table.
**Answer**

>*Query*
```sql
SELECT COUNT(distinct Grade) FROM Student;
```
>*Output*
```
+------------------------+
| COUNT(distinct(Grade)) |
+------------------------+
|                      4 |
+------------------------+
```
#### Q30. Display the details of the student(s) who is the youngest in the table.
**Answer**

>*Query*
```sql
SELECT * FROM Student WHERE Dob in (SELECT MAX(Dob) FROM Student); 
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    5 | Sarchin | M      | 2001-12-23 |   400 |   80.00 | C     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q31. Write the Output for the following
### Q31.1
**Answer**

>*Qurey*
```sql
    SELECT MAX(Dob), MIN(Dob), SUM(Total)
    FROM Student
    WHERE Dob BETWEEN '2001-01-01' AND '2001-12-31';
```
>*Output*
```
+------------+------------+------------+
| MAX(Dob)   | MIN(Dob)   | SUM(Total) |
+------------+------------+------------+
| 2001-12-23 | 2001-04-02 |       2083 |
+------------+------------+------------+
```
### Q31.2
>*Qurey*
```sql
    SELECT COUNT(*), MAX(Total), MIN(Total)
    FROM Student
    WHERE Grade IN ('A','B');
```
>*Output*
```
+----------+------------+------------+
| COUNT(*) | MAX(Total) | MIN(Total) |
+----------+------------+------------+
|        5 |        490 |        407 |
+----------+------------+------------+
```
### Q31.3
>*Query*
```sql
    SELECT SUM(Total + 5)
    FROM Student
    WHERE Grade='D';
```
>*Output*
```
+----------------+
| SUM(Total + 5) |
+----------------+
|            360 |
+----------------+
```
### Q31.4
>*Qurey*
```sql
    SELECT AVG(Total / 5)
    FROM Student;
```
>*Output*
```
+----------------+
| AVG(Total / 5) |
+----------------+
|    84.73333333 |
+----------------+
```
#### Q32. Display the count of gender based on gender.
**Answer**

>*Query*
```sql
SELECT Gender,COUNT(Gender) FROM Student GROUP BY Gender;
```
>*Output*
```
+--------+---------------+
| Gender | count(Gender) |
+--------+---------------+
| F      |             3 |
| M      |             6 |
+--------+---------------+
```
#### Q33. Display the maximum and minimum marks obtained by the students grade wise.
**Answer**

>*Query*
```sql
SELECT MAX(Total), MIN(Total),Grade FROM Student GROUP BY Grade;
```
>*Output*
```
+------------+------------+-------+
| MAX(Total) | MIN(Total) | Grade |
+------------+------------+-------+
|        490 |        470 | A     |
|        415 |        407 | B     |
|        400 |        400 | C     |
|        355 |        355 | D     |
+------------+------------+-------+
```
#### Q34. Display the maximum and minimum total of the students born in the year 2001 based on their grade.
**Answer**

>*Query*
```sql
SELECT MAX(Total), MIN(Total),Grade FROM Student WHERE year(Dob)='2001' GROUP BY Grade;
```
>*Output*
```
+------------+------------+-------+
| MAX(Total) | MIN(Total) | Grade |
+------------+------------+-------+
|        476 |        470 | A     |
|        415 |        407 | B     |
|        400 |        400 | C     |
+------------+------------+-------+
```
#### Q35. Display the number of students grade wise where grades include A and B.
**Answer**

>*Query*
```sql
SELECT COUNT(Grade),Grade FROM Student WHERE Grade='A' OR Grade='B' GROUP BY Grade;
```
>*Output*
```
+--------------+-------+
| COUNT(Grade) | Grade |
+--------------+-------+
|            3 | A     |
|            2 | B     |
+--------------+-------+
```
#### Q36. Display the number of students grade wise where number of students in each grade is more than two.
**Answer**

>*Query*
```sql
SELECT COUNT(Grade),Grade FROM Student GROUP BY Grade HAVING COUNT(Grade)>2;
```
>*Output*
```
+--------------+-------+
| COUNT(Grade) | Grade |
+--------------+-------+
|            3 | A     |
|            3 | C     |
+--------------+-------+
```
#### Q37. Update Varun's date of birth to 12th November 2000.
**Answer**

>*Query*
```sql
UPDATE STUDENT SET Dob='2000-11-12' WHERE Sname='Varun';
  SELECT * FROM Student;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-02-04 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-05-11 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-06-05 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | C     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-05-12 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q38. Increment Sarchin's mark by 10 and alter his grade to B.
**Answer**

>*Query*
```sql
 UPDATE Student SET Total=Total+10,Grade='B' WHERE Sname='Sarchin';
     SELECT * FROM Student;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-02-04 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-05-11 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-06-05 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-05-12 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q39. Create a view V1 which is an exact copy of the Student table. Display it after creation.
**Answer**

>*Query*
```sql
CREATE view v1 as SELECT * FROM student;
SELECT * FROM v1;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q40. Create a view V2 which contains roll number and name of all the 'A' graders.
**Answer**

>*Query*
```sql
CREATE view v2 as SELECT Roll,Sname FROM Student WHERE Grade='A';
```
>*Output*
```
Query OK, 0 rows affected
```
#### Q41. Display the contents of the new view V2.
**Answer**

>*Query*
```sql
SELECT * FROM v2;
```
>*Output*
```
+------+---------+
| Roll | Sname   |
+------+---------+
|    4 | Shivani |
|    8 | Varun   |
|    9 | Rekha   |
+------+---------+
```
#### Q42. Create a view V3 that has a a copy of roll number and name of all the 'A' graders but with new column names. Display the view after creation.
**Answer**

>*Query*
```sql
CREATE view v3 as SELECT Roll as RollNo., Sname as StuName FROM Student WHERE Grade='A';
SELECT * FROM v3;
```
>*Output*
```
+---------+---------+
| RollNo. |StuName  |
+---------+---------+
|       4 | Shivani |
|       8 | Varun   |
|       9 | Rekha   |
+---------+---------+
```
#### Q43. Add a new column age of appropriate data type to the existing table and fill the age.
**Answer**

>*Query*
```sql
ALTER table Student ADD Age int;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade | Age  |
+------+---------+--------+------------+-------+---------+-------+------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     | NULL |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     | NULL |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     | NULL |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     | NULL |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     | NULL |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     | NULL |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     | NULL |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     | NULL |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     | NULL |
+------+---------+--------+------------+-------+---------+-------+------+
```
>*Query*
```sql
UPDATE Student SET Age = Truncate(DATEDIFF(CURRENT_DATE,Dob)/365,0);
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade | Age  |
+------+---------+--------+------------+-------+---------+-------+------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |   19 |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |   19 |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |   20 |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |   19 |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |   19 |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |   20 |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |   19 |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |   20 |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |   20 |
+------+---------+--------+------------+-------+---------+-------+------+
```
#### Q44. Remove the column age from the Student table.
**Answer**

>*Query*
```sql
ALTER table Student DROP Age;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q45. Alter the Average column to FLOAT(10, 2).
**Answer**

>*Query*
```sql
DESC Student;
```
>*Output*
```
+---------+---------------+------+-----+---------+-------+
| Field   | Type          | Null | Key | Default | Extra |
+---------+---------------+------+-----+---------+-------+
| Roll    | int(11)       | NO   |     | NULL    |       |
| Sname   | char(15)      | YES  |     | NULL    |       |
| Gender  | char(2)       | YES  |     | NULL    |       |
| Dob     | date          | YES  |     | NULL    |       |
| Total   | int(11)       | YES  |     | NULL    |       |
| Average | decimal(10,2) | YES  |     | NULL    |       |
| Grade   | char(2)       | YES  |     | NULL    |       |
+---------+---------------+------+-----+---------+-------+
```
>*Query*
```sql
SELECT * FROM Student;
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
>*Query*
```sql
ALTER table Student MODIFY column Average FLOAT(10,2);
```
>*Query*
```sql
DESC Student;
```
>*Output*
```
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| Roll    | int(11)     | NO   |     | NULL    |       |
| Sname   | char(15)    | YES  |     | NULL    |       |
| Gender  | char(2)     | YES  |     | NULL    |       |
| Dob     | date        | YES  |     | NULL    |       |
| Total   | int(11)     | YES  |     | NULL    |       |
| Average | float(10,2) | YES  |     | NULL    |       |
| Grade   | char(2)     | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
```
>*Query*
```sql
SELECT * FROM Student
```
>*Output*
```
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    3 | Bharath | M      | 2000-11-05 |   355 |   71.00 | D     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q46. Display the value of Total / 5 for every female student and give a new column name.
**Answer**

>*Query*
```sql
SELECT Total/5 as AMF FROM Student WHERE Gender='F';
```
>*Output*
```
+----------+
| AMF      |
+----------+
|  95.2000 |
|  80.0000 |
|  98.0000 |
+----------+
```
#### Q47. Display the student name, parent name and address of all the students.
**Answer**

>*Query*
```sql
SELECT Student.Sname, Personal.Parent, Personal.Address FROM Student INNER JOIN Personal WHERE Student.Roll = Personal.Roll;
```
>*Output*
```
+---------+--------+------------------+
| Sname   | Parent | Address          |
+---------+--------+------------------+
| Ajay    | ABC    | 1st Cross Street |
| Bharath | XYZ    | 2nd Cross Street |
| Shivani | PQR    | 3rd Cross Street |
| Kamala  | LMN    | 4th Cross Street |
| Rekha   | ABCD   | 5th Cross Street |
+---------+--------+------------------+
```
#### Q48. Display the roll number, student name and parent name of all 'A' graders.
**Answer**

>*Query*
```sql
SELECT Student.Roll,Student.Sname, Personal.Parent FROM Student INNER JOIN Personal on Student.Roll = Personal.Roll WHERE Grade='A';
```
>*Output*
```
+------+---------+--------+
| Roll | Sname   | Parent |
+------+---------+--------+
|    4 | Shivani | PQR    |
|    9 | Rekha   | ABCD   |
+------+---------+--------+
```
#### Q49. Remove the details of those students from the Student table who have got 'D' grade.
**Answer**

>*Query*
```sql
DELETE FROM Student WHERE Grade='D' SELECT * FROM Student;
```
>*Output*
```
Query OK, 1 row affected
+------+---------+--------+------------+-------+---------+-------+
| Roll | Sname   | Gender | Dob        | Total | Average | Grade |
+------+---------+--------+------------+-------+---------+-------+
|    1 | Anand   | M      | 2001-05-13 |   407 |   81.40 | B     |
|    2 | Ajay    | M      | 2001-04-02 |   400 |   80.00 | C     |
|    4 | Shivani | F      | 2001-05-06 |   476 |   95.20 | A     |
|    5 | Sarchin | M      | 2001-12-23 |   410 |   80.00 | B     |
|    6 | Dhoni   | M      | 2000-11-17 |   415 |   83.00 | B     |
|    7 | Kamala  | F      | 2001-12-05 |   400 |   80.00 | C     |
|    8 | Varun   | M      | 2000-11-12 |   470 |   94.00 | A     |
|    9 | Rekha   | F      | 2000-10-15 |   490 |   98.00 | A     |
+------+---------+--------+------------+-------+---------+-------+
```
#### Q50. Remove the Student table from the database.
**Answer**

>*Query*
```sql
DROP table Student;
```
>*Output*
```
 Table 'sqlpractice.student' doesn't exist
```
