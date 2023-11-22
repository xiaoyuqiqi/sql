# SQL初始化常用语句

### 1.mysql建表语句  如果不存在表则创建 （IF NOT EXISTS）

```sql
CREATE TABLE IF NOT EXISTS  `table` (
  `id` bigint(20) NOT NULL COMMENT '主键id',
  `mark` longtext COMMENT '备注',
  `score` bigint(20) DEFAULT NULL COMMENT '分数',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='表备注';
```

### 2.mysql添加字段语句

```sql
ALTER TABLE `表名`
ADD COLUMN  `字段1` VARCHAR(255)  DEFAULT NULL COMMENT '备注',
ADD COLUMN  `字段2` int(4) DEFAULT NULL COMMENT '备注';
```

### 3.mysql修改字段

```SQL
ALTER  TABLE `表名`  CHANGE COLUMN `旧字段名` `新字段名` bigint(20) ;
```



