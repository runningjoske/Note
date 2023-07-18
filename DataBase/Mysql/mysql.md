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

