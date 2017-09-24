- DDL： *改变表结构*
- DML： *针对数据，可以回退*
- 超码
  - 一个或多个属性集合
  - 可唯一标识一个元组
- 候选码
  - 最小超码
- 主码
  - 候选码
  - 自定义
- 外码
  - 关系r1的属性e
  - e为关系r2的主码
  - e即为r1上参照r2的外码
  - r1为e依赖的参照关系
  - r2为e的被参照关系
  ``` txt
  运动员国籍代码与国家表
  ```

*数据类型*

|       name     |        type        |
|       ---      |        ---         |
|     char(n)    |    长度为n的字符串  |
|   varchar(n)   |  最大长度为n的可变长|
|      int       |    integer         |
|   numeric(p,d) |  p位，d位小数       |
|   FLOAT(n)     |   精度至少为n       |

``` DDL
CREATE table inventory
      ( id int,
        name varchar(20)
        primary key (id) not null);
INSERT INTO inventory
    VALUES(1,'Apple')
INSERT INTO inventory
    VALUES(2,'Banana')

```

##### * inventory *
| id  | name  |
| --- | ---   |
| 1   | Apple |
| 2   | Banana|

*顺序*
``` DML
SELECT

FROM

WHERE

GROUP BY

HAVING

ORDER BY


```

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

* DELETE
``` DDL
DELETE FROM inventory
WHERE id =1;                //delete mete
DELETE FROM inventory;    //保留关系
```

* DROP
``` DDL
DROP TABLE inventory      //delete ALL
```

* ALTER
``` DDL
ALTER TABLE inventory A D;
ALTER TABLE DROP A;
```

| 运算符 | 描述  |
| ---   |  ---  |
|  <>   |  不等于 |
| like  | 自定义 |
|between| <= AND >=|
* AND OR
``` DML
NULL AND TRUE == NULL
NULL OR  FALSE == NULL
```

* ORDER BY
  ``` DML
  ORDER BY id;
  ORDER BY 1,2;   //1相同排2
  ORDER BY 1 DESE;  //降序
  ORDER BY 1 ASC ;  //升序
  ```
*LIKE*
    ``` DML
    WHERE name LIKE 'Ap%';
    WHERE name LIKE '__%';
    WHERE name LIKE 'A\%' escape '\';   \\  '\'转义字符

    ```

*处理空值*
  ``` DML
  isnull(comm,0)
  //子函数忽略空值  
  ```

*集合运算*
  ``` DML
  //并
  union   //去重，升序
  union all //简单组合
  //交
  intersect
  //差
  except
  ```

*聚集函数*
  ``` DML
  AVG();
  MIN();
  MAX();
  sum();
  COUNT();
  //忽略null  except COUNT(*);
  ```

*分组聚集*
  ``` DML
  GROUP BY 2,3;
  SELECT
    - 组函数中的字段
    - GROUP BY 后的字段
    - HAVING 条件
    GROUP BY DEPTON HAVING AVG(sal)<2500
  ```

*别名*
  ``` DML
  sal*12+isnull(comm ,0 ) as "Salary Of Year"
  ```
*嵌套子查询*
  - 独立子查询
    ```DML
    SELECT id
    FROM inventory
    WHERE name=(SELECT name
                FROM inventory
                WHERE name='Apple');
    ```
  - 相关子查询
  ```DML
  SELECT id
  FROM inventory e             //别名 e
  WHERE name=(SELECT name
              FROM inventory
              WHERE e.name='Apple');
  ```
  - in
    - = ANY
  - not in
    ```DML
    500 not in (1000,3000,null)
    ```
  - > ALL
  - exists
  - not exists

- 知识点
  ``` DML
  * ROUND( CAST ( COUNT (COMM) AS FLOAT) )/COUNT(*),12)
    * ROUND(NUM,12)       //保留小数点后12位
    * CAST(INT AS FLOAT)  //类型强制转换
  ```
