#### select
`select cust_name
from customers;`

#### distinct
`select distinct customers.cust_name
from customers;`

#### limit pos,row
`select customers.cust_name
from customers
limit 0,3;`

#### order by /desc
`select cust_name
from customers
order by cust_name desc ;`

#### where
`select cust_name
from customers
where cust_name='Wascals';`

#### in 效率高
`select cust_name
from customers
where cust_name in ('Wascals');`

#### like
`select cust_name
from customers
where cust_name like 'Was%s';`

#### group by
`select vend_id,count(*) as num_prod
from products
group by vend_id;`

#### group by + having
`select vend_id,count(*) as num_prod
from products
group by vend_id
having num_prod>2;`

#### subquery

`select cust_name
from customers
where cust_id in (
    select cust_id
    from orders
    where order_num in
          (SELECT order_num
           FROM orderitems
           where prod_id = 'TNT2')
)`

#### 联结查询 where
`select cust_name
from customers
where cust_id in (
    select cust_id
    from orders
    where order_num in
          (SELECT order_num
           FROM orderitems
           where prod_id = 'TNT2')
)
`
#### 联结查询 join
`select cust_name
from customers
join orders on customers.cust_id=orders.cust_id
join orderitems on orders.order_num=orderitems.order_num and orderitems.prod_id = 'TNT2'
`

#### left join/right join
`select cust_name
from customers
join orders on customers.cust_id=orders.cust_id
left join orderitems on orders.order_num=orderitems.order_num and orderitems.prod_id = 'TNT2'
`

#### 组合查询



#### alter
`alter table customers
    add cust_o varchar(100);`
    
`alter table customers
    drop cust_o;
`



