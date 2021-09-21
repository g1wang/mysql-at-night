### 03-PROCEDURE

- 多个处理逻辑封装

```
//drop
drop procedure countCust;

//create
create procedure countCust()
BEGIN
    select count(cust_id)
        from customers;
end;

//call
call countCust;
```

