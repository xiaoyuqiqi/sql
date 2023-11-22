# SQL常用函数

### 1.LOWER()和UPPER()

#### 1.介绍

`LOWER()` 和 `UPPER()` 是 MySQL 中的字符串函数，分别用于将字符串转换为小写和大写。

1. **LOWER() 函数：**
   `LOWER()` 函数用于将字符串中的字符转换为小写。它的语法如下：
   
   ```sql
   LOWER(str)
   ```
   
   其中，`str` 是要转换为小写的字符串。这个函数会返回一个新的字符串，其中 `str` 中的所有字符都转换为小写形式。

   示例：
   ```sql
   SELECT LOWER('Hello World'); -- 输出结果：hello world
   ```
   
2. **UPPER() 函数：**
   `UPPER()` 函数用于将字符串中的字符转换为大写。它的语法如下：
   
   ```sql
   UPPER(str)
   ```
   
   其中，`str` 是要转换为大写的字符串。这个函数会返回一个新的字符串，其中 `str` 中的所有字符都转换为大写形式。

   示例：
   ```sql
   SELECT UPPER('Hello World'); -- 输出结果：HELLO WORLD
   ```

这两个函数在处理字符串时非常有用，可以根据需要将字符串转换为统一的大小写形式进行比较、显示或处理。

#### 2.使用场景

1.不区分大小写的模糊搜索

使用 `LOWER()` 或 `UPPER()` 函数：

另一种方法是将列或要匹配的值转换为小写或大写，然后再进行比较。例如：

```sql
SELECT *
FROM your_table
WHERE LOWER(your_column) LIKE LOWER('%your_value%');
```

或者

```sql
SELECT *
FROM your_table
WHERE UPPER(your_column) LIKE UPPER('%your_value%');
```

这些方法会将列或要匹配的值转换为小写或大写，然后再进行模糊匹配比较。

需要注意的是，这些方法可能会导致索引失效，因为它们会改变列的内容，使得无法使用索引来加速查询。在实际使用时，应该根据实际情况和需求来选择合适的方法，并对性能进行评估。

```sql
 <select id="sqlId" resultMap="findMetadataInfoMap">
        SELECT
        *
        FROM
        tablename
        WHERE 1 = 1 AND LOWER(METADATA.NAME) LIKE LOWER(&apos;%${name}%&apos;)
    </select>
```

