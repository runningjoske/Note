mysql 常用语句



索引操作

```
//添加主键索引（PRIMARY KEY）
ALTER TABLE table_name ADD PRIMARY KEY ( column)

//添加普通索引（INDEX） 
ALTER TABLE table_name ADD INDEX index_name ( column ) 

//添加唯一索引（UNIQUE）
ALTER TABLE table_name ADD UNIQUE (column) 

//添加全文索引（FULLTEXT）
ALTER TABLE table_name ADD FULLTEXT ( column) 

//添加复合索引
ALTER TABLE table_name ADD INDEX index_name ( column1, column2, column3 )

//删除索引
DROP INDEX index_name ON table

```

报错 sql_mode=only_full_group_by

```

//查看mysql配置
select @@global.sql_mode;

//剔除返回结果中的ONLY_FULL_GROUP_BY ，然后重新set进去
SET GLOBAL sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';

//再次查看mysql配置，是否ONLY_FULL_GROUP_BY已剔除

```

