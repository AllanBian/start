## Mysql速查
以下内容参考[易百教程][易百教程],仅用于个人能够在单页上查询

### 查询数据

- SELECT 语句

```SQL
SELECT lastname, firstname, jobtitle FROM employees;
<!--
// 复杂的SELECT语句
SELECT
    column_1, column_2, ...
FROM
    table_1
[INNER | LEFT |RIGHT] JOIN table_2 ON conditions
WHERE
    conditions
GROUP BY column_1
HAVING group_conditions
ORDER BY column_1
LIMIT offset, length;
 -->
```

- SELECT DISTINCT 语句

与SELECT语句一起组合来消除结果集中的重复行<br>
如果在SELECT语句中使用GROUP BY子句,而不是用聚合函数,则GROUP BY子句的行为与DISTINCT类似

```SQL
SELECT DISTINCT
    state, city
FROM
    customers
WHERE
    state IS NOT NULL
ORDER BY
    state ,city;
```


### 过滤数据
- WHERE 语句

```SQL
SELECT
    lastname, firstname, officeCode
FROM
    employees
WHERE
    officecode <= 4;
```

- AND 运算符

```SQL
SELECT
    customername, country, state
FROM
    customers
WHERE
    country = 'USA' AND state = 'CA';
```

- OR 运算符

```SQL
SELECT
    customername, country
FROM
    customers
WHERE
    country = 'USA' OR country = 'France';
```

- IN 运算符

在WHERE子句中使用IN运算符来确定值是否匹配列表或子查询中的指定值

```SQL
SELECT
    officeCode, city, phone, country
FROM
    offices
WHERE
    country
IN ('USA' , 'France');
```

- BETWEEN 运算符

```SQL
SELECT
    productCode, productName, buyPrice
FROM
    products
WHERE
    buyPrice BETWEEN 90 AND 100;
```


- LIKE 运算符

```SQL
SELECT
    employeeNumber, lastName, firstName
FROM
    employees
WHERE
    lastname LIKE '%on%';
```

- LIMIT 子句

```SQL
SELECT
    customernumber, customername, creditlimit
FROM
    customers LIMIT 5;
```


- IS NULL

```SQL
SELECT
    customerName, country
FROM
    customers
WHERE
    salesrepemployeenumber IS NULL
ORDER BY
    customerName;
```

### 排序数据
- ORDER BY 自定义排序 默认升序ASC

```SQL
SELECT
    contactLastname, contactFirstname
FROM
    customers
ORDER BY
    contactLastname DESC;
```

- ORDER BY 自然排序
如果无法理解可以参阅[自然排序][自然排序]

```SQL
SELECT
    item_no
FROM
    items
ORDER BY
    LENGTH(item_no) , item_no;
```

### 连接表
- Mysql 别名

```SQL
SELECT
    CONCAT_WS(' ', lastName, firstname) `Full name`
FROM
    employees
ORDER BY
    `Full name`;
```

- INNER JOIN 内部联接

```SQL
SELECT
    productCode, productName, textDescription
FROM
    products t1
INNER JOIN
    productlines t2
ON
    t1.productline = t2.productline;
等价
SELECT
    productCode, productName, textDescription
FROM
    products
INNER JOIN
    productlines
USING (productline);
```

- LEFT JOIN

```SQL
SELECT
    c.customerNumber,
    c.customerName,
    orderNumber,
    o.status
FROM
    customers c
LEFT JOIN orders o ON c.customerNumber = o.customerNumber;
```

- RIGHT JOIN

```SQL
SELECT
    c.customerNumber,
    c.customerName,
    orderNumber,
    o.status
FROM
    customers c
RIGHT JOIN orders o ON c.customerNumber = o.customerNumber;
```

- CROSS JOIN
如果无法理解可以参阅[CROSS JOIN][CROSS JOIN]

```SQL
SELECT
    b.store_name,
    a.product_name,
    IFNULL(c.revenue, 0) AS revenue
FROM
    products AS a
        CROSS JOIN
    stores AS b
        LEFT JOIN
    (SELECT
        stores.id AS store_id,
        products.id AS product_id,
        store_name,
            product_name,
            ROUND(SUM(quantity * price), 0) AS revenue
    FROM
        sales
    INNER JOIN products ON products.id = sales.product_id
    INNER JOIN stores ON stores.id = sales.store_id
    GROUP BY store_name , product_name) AS c ON c.store_id = b.id
        AND c.product_id= a.id
ORDER BY b.store_name;
```

- 自连接

```SQL
SELECT
    CONCAT(m.lastname, ', ', m.firstname) AS 'Manager',
    CONCAT(e.lastname, ', ', e.firstname) AS 'Direct report'
FROM
    employees e
        INNER JOIN
    employees m ON m.employeeNumber = e.reportsto
ORDER BY manager;
```

### 分组数据
- GROUP BY 子句

```SQL
SELECT status, COUNT(*) AS total_number FROM orders GROUP BY status;
```

- HAVING 子句
HAVING子句通常与GROUP BY子句一起使用,以根据指定的条件过滤分组

```SQL
SELECT
    ordernumber,
    SUM(quantityOrdered) AS itemsCount,
    SUM(priceeach*quantityOrdered) AS total
FROM
    orderdetails
GROUP BY ordernumber
HAVING total > 55000;
```

### Mysql子查询,派生表,通用表达式
- Mysql子查询
- Mysql派生表
- Mysql通用表达式
- 递归CTE遍历分层数据

### 使用SET操作符
- UNION 和 UNION ALL
- INTERSECT 模拟

### 修改数据
- INSERT 语句
- INSERT IGNORE 忽略错误
- UPDATE 语句
- UPDATE JOIN 语句
- DELETE 删除数据
- ON DELETE CASCADE
- DELETE JOIN 多表删除数据
- REPLACE 语句
- PREPARE 语句

### Mysql事务
- Mysql事务
- Mysql表锁定

### 管理Mysql数据库和表
- Mysql数据库管理
- Mysql表类型
- CREATE TABLE 创建新表
- Mysql序列
- ALTER TABLE 修改表结构
- RENAME TABLE 重命名表
- ALTER TABLE DROP COLUMN 从表中删除列
- ALTER TABLE ADD COLUMN 向表中添加新列
- DROP TABLE 删除表
- Mysql临时表
- TRUNCATE TABLE 删除表中的所有数据



[易百教程]: https://www.yiibai.com/mysql/basic-mysql.html
[自然排序]: https://www.yiibai.com/mysql/natural-sorting.html
[CROSS JOIN]: https://www.yiibai.com/mysql/cross-join.html
