lightning bolt = running it, where to look for problems
Everything in the window is run when pressed

To run one line, put cursor over it and the other lightning bolt

show databases; ,shows databases in the system  

SQL doesnt care about carriage returns

show tables in spartan_learning;

use sparta_learning; , so SQL just uses this database

shows columns in people; ,look specifically at a section
can also use describe people; ,describes table

char, fixed length, we call a limit.
varchar, accept anything upto 255 char.
datetime,
date,
time,
bigint, more memory
small int, less memory
int,
float, decimal
boolean,
blob, big chunk of code, could be used to store a big chunk of text
binary, a chunk of binary

Null, is it allowed to be empty
Key, primary key?

select first_name fromn people, get the column first name from the table people
select first_name, surname from people, get back 2 columns
select first_name, surname, department from people;, get back 3 columns
select * from people; , shows all the rows and all the columns

select * from people where person_id = 2; , filtering out a specific row, user
select * from people where person_id <> 2;, not equal to (!=), get me everyone apart 
from dave
select * from people where rating > 5;, row where rating is higher than 5
<
=>
<=
select * from people where first_name = 'Joe'; 
select * from people where first_name like 'Joe';, allows us to wildcards, 
so o is a wildcard
select * from people where first_name like 'J%'; anything that starts with J
select * from people where first_name like '%e%';, anyone with an e anywhere
in their name

select * from people where t_pay > 30000 and email like '%@gmail.com'; filtering
select * from people where t_pay > 40000 or rating > 4; filtering

select * from people where t_pay > 40000 or rating > 4 order by rating; 
, specifically order them by the column rating

select * from people where t_pay > 40000 or rating > 4 order by rating desc;
, get them the right way round, descending pay

--------------------------------------------------------------------------------

Adding Rows

insert into
people (first_name, surname, dob), the field with columns inside we want 
to put info into 
values, then the values we want it in, if we want more people/rows just 
have more rows in the values
('Tim', 'Staton', '1975-03-01')

--------------------------------------------------------------------------------

Update Row
set surname= 'Oooooops', sets everyones surname to ooops

Theres no undo in SQL itself

update people
set surname= 'Smythe'
where person_id =2; , filtering update of a row

----------------------------------------------------------------------------------

Delete Row
delete from people where person_id = 8;, filtered deletion of a row

----------------------------------------------------------------------------------

Creating a table

create table friends(
friend_id smallint(3),
name varchar(255),
height int,
is_happy boolean
);

you have to define primary keys

describe friends; ,see the description of our friends table and see if its worked

drop table friends; ,completely delete a table, be frickin careful!

no one should let you have root access, just be careful

create table friends(
friend_id smallint(3) not null primary key auto_increment,
number goes up byitself so we dont have to worry, not null prevents it from being null
name varchar(255) not null unique, makes sure name is unique (its a constraint)
height int default 160, sets up a basic default for the height
is_happy boolean not null
);

Build a more specific table so we dont accidentaly put wrong data into it

Adding friends e.g. 

insert into friends (name, height, is_happy)
values ('Jimmy', 180, true);
select * from friends;

insert into friends (name, is_happy)
values ('Tara', false);
select * from friends;

insert into friends (name)
values ('Steve');
select * from friends; ,gives an error because of is_happy
 
---------------------------------------------------------------------------------

Adding and removing columns

alter table friends
add column (weight int); 
, if we want make not null then do weight int not null

describe friends;
as you can see the weight is not set so is null

alter table friends
drop column weight;
describe friends;

-------------------------------------------------------------------------------------
Practice

alter table friends

alter is_happy set default 1; , changing the default

update friends

set name='shiblu'

where friend_id=7;

delete from friends

where friend_id=7;

show tables;

-------------------------------------------------------------------------------------

Statement is starting from the statement and finishing with the ;

Column constraints
uniq
not_null
default
primary_key
foriegn_key 
--------------------------------------------------------------------------------------

Aggregrate Functions

select first_name, t_pay, t_tax, (t_pay - t_tax) 
from people; 
, does calculation for numeric values only, 
creating a column for this calculation, we have to put it in brackets to be virtual

select count(*) from people;
, aggregrate function which counts up the number of rows in people

select count(*) from people where rating > 3;, Filtered count

select max(rating) from people; returns the highest/maximum rating

select avg(rating) from people; returns the average, always return a decimal number

select round(avg(rating), 0) from people; round the thing to 0 d.p, 
round function which we can always use for numerical values

select sum(t_pay) from people; sum of everyones pay, 

select min(column) from 

select max(t_pay), min(t_pay), avg(t_pay)
from people; , combining aggregate functions

select department, sum(t_pay)
from people
group by department; 
,gives total pay from each department and the 'department' place has to be the same

select department, sum(t_pay), count(*) , counts the number of people as well 
from people
group by department;

select department, sum(t_pay)
from people
group by department having count (*) > 1; 
,filters so departments show up where count is greater than 1

---------------------------------------------------------------------------------

Value constraints

Foriegn key constraint

To add a foriegn key constraint, prevents data integrity errors,
SQL doing it for us

pub_id int(10) references publishers(pub_id)
, so it the references the table and more specifically the pub_id

or we could do this

alter table books
add constraint foreign key(pub_id)
references publishers(pub_id);
, make sure all the foreign keys first match

so to fix
update books

set pub_id=1

where title='My Book';


then run foriegn key constraint again

thereafter you run

describe books;

You can see that the key is called MUL now.

now add a foriegn key constraint to author

alter table books

add constraint foreign key(author_id)

references authors(author_id);


The check constraint

purchases int(11) check (purchases>0), 
when creating a new row it checks if purchases are greater than 0 in this case

can chuck constraints after if we want
by calling a constraint after we can give a constraint a name e.g.

constraint unique_title unique (title)

advantage being, if we get an error we can see the constraint
so we know which error it is

---------------------------------------------------------------------------------

Users & Permissions

we are logged into SQL as root, 
so not secure and well your not meant to be in root

so create a new database user to resolve this

create user 'joe'@'localhost'
identified by 'mypassword'; 
can only do this while we are logged in as root

create user 'Shorof'@'localhost'

identified by 'Barry'; 

Grant privileges to the user, have to be in root

grant all privileges
on spartan_learning.people
to 'Shorof'@'localhost'; 
,giving permission to Shorof to access database spartan_learning and table people

as can be checked by 
show tables in spartan_learning;

grant all privileges
on spartan_learning.*
to 'joe'@'localhost';

grant all privileges
on *.*
to 'joe'@'localhost'; , root permissions

flush privileges; 
once you run a bunch of changes to users always run it at the end, clear the cache

grant select
on istore.product
to 'benny'@'localhost'; 
,so benny can only use select statements on the product table

Common permissions

All Permissions,
Create,
Drop,
Delete,
Insert,
Select,
Update, 
Grant Option, grant or remove other permissions

revoke drop on ctt.*
from 'guy'@'localhost'; 
,revoke, taking away permssion to drop in this case

deletes user
drop user 'joe'@'localhost'

--------------------------------------------------------------------------------------

Joins

Inner join

select * from employees
inner join departments
on employees.department_id=departments.id;
,only if the fields equal then you get a table back

select employees.name,departments.name from employees
inner join departments
on employees.department_id=departments.id;
,filtering but you need to call the table first, pretty useful after it

Aliases

To avoid confusion use aliases, so . . .

select employees.name as Employee,departments.name as Department 
from employees
inner join departments
on employees.department_id=departments.id;
,filtering with aliasing, can take away the as if you want

similar thing called table aliases when you give table names aliases

-------------------------------------------------------------------------------------

Practice

select 

b.isbn as ISBN, 

a.author_name as Author, 

p.publisher as Publisher, 

b.pub_year as 'Publication Year',

b.title as 'Book Title',

p.pub_address as 'Publisher Address'

from books b 

inner join authors as a

on b.author_id=a.author_id

inner join publishers as p

on b.pub_id=p.pub_id;

---------------------------------------------------------------------------------------

Outer joins

Left Outer Joins (Left Join)

you always get everything in the left hand table. 

Right Outer Joins (Right Join)

you always get everything in the right hand table.

Full Outer Joins

shows everything

----------------------------------------------------------------------------------------

Subqueries

select * from books where author_id in
(select author_id from authors
where author_name like "%s%")
,in is a operator like an =

Joins vs Subqueries
joins are more performant
joins are more powerful
subqueries are easier to read
subqueries are good for aggregate functions e.g.

select * from people where t_pay >
(select avg(t_pay) from people); 

for numerical stuff subqueries are better!

select within select is a subquery

<<<<<<< HEAD
squizoo.net

Select b.fname, v.venue, l.location 
from business b, venue v, location l 
where b.id = v.id and v.id = l.id
=======
sqlzoo.net
>>>>>>> 9d5a778dc51d370ffd57c0a1ed72dc6067ea9711
 