## Get Multiple Comments on a single ID in one row through Oracle LISTAGG.

**Use of Oracle LISTAGG**

Sometimes, you may want to aggregate data from a number of rows into a single row and associate the result row with a specific value. LISTAGG function in DBMS is used to aggregate strings from data in columns in a database table.

```
Select * from COMMENT_TABLE ;       //Query

Id      Comment        Create_DataTime
----- ----------- ---------------------- ------------------------
1      Admitted          10-10-20 12:43:00.000000000 AM
1      Completed         10-11-20 12:00:00.000000000 AM
2      Hi All            10-10-20 12:00:00.000000000 AM
2      Piya Here         10-11-20 12:00:00.000000000 AM
3      Success           10-10-20 12:00:00.000000000 AM
1      Submitted         10-10-20 12:00:00.000000000 AM
```
SQL query to group each comment in its respective ID separated by pipe ('|') with the help of the LISTAGG function and also ORDER By Create_DataTime, So, that we get comments in an ascending ordered manner on the basis of Create Data Time.

```
SELECT  ID, LISTAGG(COMMENT, ' | ') WITHIN GROUP 
(ORDER BY Create_DataTime) AS COMMENTS
FROM COMMENT_TABLE where ID in GROUP BY ID;
``` 
***Note: You can use any delimiter of your choice instead of a pipe('|').***

**Result Obtained:**

```
ID     COMMENTS
----- ----------- ---------------------- ------------------------
1      Submitted | Admitted   | Completed            
2      Hi All  |    Piya Here
3      Success  
``` 




         




