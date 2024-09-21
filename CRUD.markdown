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

Updating column without specifying specific details using ***where*** clause where update all the columns 

```
update cats set age = '14' where name ='Misty';
```

```
update cats.cats set breed='British Short Hair' where breed = 'Tabby';
```

```
update cats.cats set name = 'Jack' where name = 'Jackson'; 
```

```
select * from cats.cats where breed = 'Maine Coon';

update cats.cats set age = 10 where name = 'Dumbledore' ; 
```


## A Good Rule Of Thumb

When updating a column, first check the data to make sure it's pointing to the right rows

---
## Delete 
Used to delete data in the dataset. 
```
Delete from cats.cats where name = 'Egg'
```
---
# String Functions
### Book Dataset 

```
# Create database

Create database bookshop;

# Create table

create table bookshop.book (
book_id int primary key auto_increment,
title varchar(100),
author_fname varchar(100),
author_lname varchar(100),
released_year int,
stock_quantity int,
pages int
);

# Update table

insert into bookshop.book (
 title, author_fname, author_lname, released_year, stock_quantity, pages)
values 
('The Namesake', 'Jhumpa', 'Lahiri', 2003, 32, 291),
('Norse Mythology', 'Neil', 'Gaiman',2016, 43, 304),
('American Gods', 'Neil', 'Gaiman', 2001, 12, 465),
('Interpreter of Maladies', 'Jhumpa', 'Lahiri', 1996, 97, 198),
('A Hologram for the King: A Novel', 'Dave', 'Eggers', 2012, 154, 352),
('The Circle', 'Dave', 'Eggers', 2013, 26, 504),
('The Amazing Adventures of Kavalier & Clay', 'Michael', 'Chabon', 2000, 68, 634),
('Just Kids', 'Patti', 'Smith', 2010, 55, 304),
('A Heartbreaking Work of Staggering Genius', 'Dave', 'Eggers', 2001, 104, 437),
('Coraline', 'Neil', 'Gaiman', 2003, 100, 208),
('What We Talk About When We Talk About Love: Stories', 'Raymond', 'Carver', 1981, 23, 176),
("Where I'm Calling From: Selected Stories", 'Raymond', 'Carver', 1989, 12, 526),
('White Noise', 'Don', 'DeLillo', 1985, 49, 320),
('Cannery Row', 'John', 'Steinbeck', 1945, 95, 181),
('Oblivion: Stories', 'David', 'Foster Wallace', 2004, 172, 329),
('Consider the Lobster', 'David', 'Foster Wallace', 2005, 92, 343);
```
- The `book_id` column is auto-incremented so it does not need any values in *insert* section. 

## CONCAT
`CONCAT` function is a built-in string function that is used to concatenate two or more strings together.

```
select  concat(author_fname,' ', author_lname) as author_fullName  from bookshop.book;
```
# concat with
```
select concat_ws('-', author_fname, author_lname) full_name from bookshop.book;
```
