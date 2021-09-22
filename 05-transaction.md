###  transaction



- 事务（transaction）指一组SQL语句；
- 回退（rollback）指撤销指定SQL语句的过程；
- 提交（commit）指将未存储的SQL语句结果写入数据库表；
- 保留点（ savepoint）指事务处理中设置的临时占位符（ placeholder），你可以对它发布回退（与回退整个事务处理不同）。



```
select * from orderitems;
start transaction ;
delete from orderitems;
select  * from  orderitems;
rollback ;
select  * from  orderitems;
```

```
select * from orderitems;
start transaction ;
update  orderitems set orderitems.quantity = 3 where prod_id='FB';
select  * from  orderitems;
commit ;
select  * from  orderitems;
```

