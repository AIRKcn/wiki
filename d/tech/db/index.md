# 数据库技术

## 何谓数据库


----


## 关系型数据库 RDBMS

### MySQL

__Tips__: Range分区主要是用来按照时间分区的, 可以把一些老数据隔离开来, 甚至删掉

```sql
-- 表包含一个主键和一个唯一键
CREATE TABLE emp(
    id INT NOT NULL,
    store_id INT NOT NULL,
    PRIMARY KEY(id),
    UNIQUE KEY key_store_id(store_id)
)
-- 在主键上分区
PARTITION BY RANGE(id)(
    PARTITION p0 VALUES LESS THAN (10),
    PARTITION p1 VALUES LESS THAN (20),
    PARTITION p2 VALUES LESS THAN (30)
);
```

### Microsoft SQL Server

### Oracle

### PgSQL

----

## Key-Value数据库 NoSQL

### Redis

### Memcache

#### 基于Memcache协议扩展或变化的数据库(缓存)系统

----


## 其它类型数据库

### 对象数据库

#### ?

### 文档型数据库

#### MongoDB


### 列数据库

#### BigTable
