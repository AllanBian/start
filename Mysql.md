## Mysql速查
以下内容参考[易百教程][易百教程],仅用于个人查询

### 查询数据
- SELECT 语句
```
SELECT lastname, firstname, jobtitle FROM employees;
或者
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
```
- SELECT DISTINCT 语句
### 过滤数据
- WHERE 语句
- AND 运算符
- OR 运算符
- IN 运算符
- BETWEEN 运算符
- LIKE 运算符
- LIMIT 子句
- IS NULL

### 排序数据
- ORDER BY 自定义排序
- ORDER BY 自然排序

### 连接表
- Mysql 别名
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- CROSS JOIN
- 自连接

### 分组数据
- GROUP BY 子句
- HAVING 子句

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
