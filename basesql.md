###select
select cust_name
from customers;

###distinct
select distinct customers.cust_name
from customers;

### limit pos,row
select customers.cust_name
from customers
limit 0,3;

### order by /desc
select cust_name
from customers
order by cust_name desc ;

### where
select cust_name
from customers
where cust_name='Wascals';

### in 效率高
select cust_name
from customers
where cust_name in ('Wascals');

### like
select cust_name
from customers
where cust_name like 'Was%s';

### group by
select vend_id,count(*) as num_prod
from products
group by vend_id;

### group by + having
select vend_id,count(*) as num_prod
from products
group by vend_id
having num_prod>2;




