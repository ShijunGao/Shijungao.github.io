#### SQL Server Note
##### * inventory *
| id  | name  |
| --- | ---   |
| 1   | Apple |
| 2   | Banana|


* SELECT
  ``` DML
  SELECT id FROM inventory
  SELECT * FROM inventory        //SELECT ALL
  SELECT DISTINCT * FROM inventory      //去重，放在列之前
  ```
* WHERE
  ``` DML
  //条件
  SELECT * FROM inventory
  WHERE id = 1  ||  WHERE name = 'Apple'  ||  WHERE name is null
  ```


| 运算符 | 描述  |
| ---   |  ---  |
|  <>   |  不等于 |
| like  | 自定义 |
* AND OR
  * NULL AND TRUE =NULL
  * NULL OR  FALSE= NULL
* ORDER BY
  * ORDER BY 3,2
* INSERT
  * INSERT INTO inventory VALUES (3, ' Banana')
* GROUP BY

* isnull()==nvl()
* sal*12+isnull(comm ,0 ) as "Salary Of Year"
* WHERE ENAME LIKE '__o%'

* ORDER BY ID DESE OR ASC
* MAX()   MIN()
* ROUND( CAST ( COUNT (COMM) AS FLOAT) )/COUNT(*),12)
  * ROUND(NUM,12)
  * CAST(INT AS FLOAT)
* GROUP BY DEPTON HAVING AVG(sal)<2500
  * HAVING
