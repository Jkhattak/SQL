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
## concat with
```
select concat_ws('-', author_fname, author_lname) full_name from bookshop.book;
```
## Substring or Substr

```
select substring("Hello World', start(int), length(int)) from table
````
```
select concat(substr(title, 1, 10), '...') as title from bookshop.book;
```

## Replace
Replace parts of strings

```
select replace('Hello world', 'Hell', 'Mell')

--output--
Mello world
```
## Reverse

Reverse the provided string
```
select reverse('hello world');
```

## Char_length

Number of characters 

## lenght

Number of bytes

## Upper and Lower

Will upper character or lower characters base on function

```
select upper('hello world')
select ucase('hello world')

select lower('hello world')
select lcase('hello world')
```

## Left

left most characters from string 

```
select ("hello', 3)
```

## Repeat

Repeat string 

```
select ('Hello', 3)
```

## Trim 

```
select trim('  hello   world');

select trim(both '.' from '....this is a test...')
```
---

# Refining Selections

## Like Operation 

- % &rarr; Wildcards

- `Da%` &rarr; All the characters that *starts* with `Da`

- `%ve` &rarr; All the characters that *ends* with `ve`

- `%ve%` &rarr; All the characters that *have* `ve`
- `'% \% %; &rarr; If the character contains `%` sign

### Like vs Ilike

`LIKE`

- Case-sensitive: It matches patterns exactly as specified, including the case of the letters.

`ILIKE`

- Case-insensitive: It matches patterns regardless of the case of the letters.

## Data Analysis Operations

- `count(*)` &rarr; Count number of rows in the table
- `count(fname)` &rarr; All the *not-null* fields will be counted


## Group By
Group by summarizes or aggregates identical data into single rows

## Min and Max

`Min` helps find minimum value and `max` helps find maximum value

***Caution : Aggregation

# Data Types

## Char

Allow to store text. Char if fixed length. Every string store will be of that size

`Char(3)` &rarr; is fixed and it will store only three characters long string. Smaller characters are filled with gapped to fill the gap 

## Varchar 

Varchar only cares about it's maximum length and does not care about the size

![alt text](image-1.png)