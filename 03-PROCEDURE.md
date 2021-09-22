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

- 参数 in out @var

```
drop procedure countProd;

-- name countProd
create procedure countProd(in oprodid varchar(20), in count boolean, out ototal decimal(8, 2))
BEGIN
    -- declare ototal
    declare total decimal(8, 2);
    select count(prod_id)
    from products
    where prod_id = oprodid
    into total;
    -- is count
    if count then
        select total into ototal;
    end if;
end;

call countProd('TNT2',true, @ototal);
select @ototal;

```

