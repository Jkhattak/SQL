# CRUD
- C = Create
- R = Read
- U = Update
- D = Delete
---
## Read
Reading from a table in SQL uses the ***Select*** funcation

```
select * from cat.cats;
```
- This will *select* everything from cats table

We can also select specific columns as well

```
select name, age from cat.cats;
```

## Where
- It allows user to narrow the data. 
- It can be used with update as well
  
```
select name,age from cat.cats
where age=2;
```

## Aliases

Used primarly to make it easier to read results

```
select cat_id as id from cat.cats;

```
---
## Update

How do we alter existing data? 

- Updating column without specifying specific details using ***where*** clause where update all the columns 

```
update cats set age = '14' where name ='Misty';
```
