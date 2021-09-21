### VIEW
- 重用SQL语句。
- 简化复杂的SQL操作。在编写查询后，可以方便地重用它而不必知道它的基本查询细节。
- 使用表的组成部分而不是整个表。
- 保护数据。可以给用户授予表的特定部分的访问权限而不是整个表的访问权限。
- 更改数据格式和表示。视图可返回与底层表的表示和格式不同的数据。
- 性能问题：每次使用视图都必须处理查询执行时所需的任一个检索。复杂的视图可能导致性能下降厉害

```
create view prodcust as
    select prod_id,cust_name
from customers,orders,orderitems
where customers.cust_id = orders.cust_id and orders.order_num = orderitems.order_num;

select * from prodcust
where prod_id = 'TNT2'
```

