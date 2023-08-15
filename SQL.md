# SQL

## SQL Server

__DDL__ _Data Definition Language_ <br/>
Like CREATE, ALTER or DROP. <br/>

__DML__ _Data Manipulation Language_ <br/>
Like SELECT, INSERT, UPDATE, DELETE <br/>

__DCL__ _Data Control Language_ <br/>
COMMIT, ROLLBACK, GRANT, REVOKE <br/>

__Schema__ <br/>

Set of Databases oriented to the user <br/>

<br/>

>sp_help 'table'

Shows the _structure_ of the table 'table' and timestamp of creation. <br/>
We can use the same for _stored procedures_ and _views_ <br/>
<br/>

>sp_helptext 'view'

Shows the code from a _stored procedure_ or _view_ <br/>
<br/>

>sp_columns 'table'

Shows more info from a table. <br/>
<br/>

>select * from sys.tables

List __ALL__ the tables <br/>
<br/>

>select table_name from information_schema.tables
>where table_type = 'base table' order by 'table_name'

List all __SCHEMAS__ and tables <br/>
<br/>

>sp_helpconstraint table

Shows restrictions from the table <br/>
<br/>

>sp_depends procedure

Shows if an object depends of procedure <br/>
<br/>


### DECLARE

```sql
declare @hola int;
set @hola = 0;
print @hola;
```

### getDate()

Used to get the current stamp time. <br/>

```sql
select getDate()
```

### CONVERT

__convert(type(length), getDate(), style)__ <br/>

>select convert(char(10), getDate(), 126)

Styles: <br/>
__102__ 2015.01.09 <br/>
__103__ 19/01/2015 <br/>
__104__ 19.01.2015 <br/>
__105__ 19-01-2015 <br/>
__106__ 19 Jan 2015 <br/>
__107__ Jan 19, 2015 <br/>
__108__ 09:18:27 <br/>
__126__ 2015-01-19 <br/>

### datepart

>select datepart(day, getDate())

We can use: __month__, __hour__, __year__, __minute__, __second__, __week__


### datediff

>select datediff(day, '2005/10/28', '2006/10/28')
365 <br/>

We can use: __month__, __hour__, __year__, __minute__, __second__, __week__

### CASE

```sql
select productid,
  case categoryid
    when 1 then 'Beverages'
    when 2 then 'Condiments'
    when 3 then 'Confections'
    else 'Other'
  end as categoryName
from products
```

### LIKE

```sql
select * from books where author like '%Borges%'
```

### CAST

```sql
select 'Result: ' + cast(14.8 as varchar)
```

### DISTINCT

```sql
select distinct publicist from books
```

### ORDER BY

```sql
select title, price from books order by price
```

### TOP

```sql
select top 5 tittle as book from books
```

### PARTITION BY

```sql
select distinct status_pay, coun(*) 
over (partition by status_payment) as total
from payment
```

### OVER

```sql
select id, ROW_NUMBER() over(order by id) as Row from student
```

### GROUP BY

```sql
select wd_key, count(*) as how_many
from withdrawal group by reason order by wd_key
```

### HAVING
Is the __where__ of the _Group by_ <br/>

```sql
select wd_key, count(*) as how_many
from withdrawal group by reason having wd_key > 1000
```

### IN

```sql
select * from student
where id in (140032, 130272, 110723)

```

__Trick to add ORDER BY in a View__ <br/>

```sql
create view ReverseOrder
as
select top 100 percent * from documents
order by id desc
go
```

### TRIGGERS

* Is a Stored Procedure that runs when we try to modify data on a table.
* Can not be invoked directly.
* Do not get or return values.
* Acts just in one table.

```sql
create trigger trg_forbid
  on books
  for update
  as
    raiserror('Data can not be modified', 10, 1)
    rollback transaction
```

__instead of__


```sql
create trigger trg_employee
  on view_clients
  instead of insert
  as
    
```
