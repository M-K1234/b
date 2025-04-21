Assignment 04b  
**Documentation for database and research**  
By Muhammad Ali Khan

**Introduction**

I have created a database using PostgreSQL, which is hosted for free on:  

[https://www.neon.tech](https://www.neon.tech) 

The database is called *it\_firm* and has a schema called personel, which contains a table called employees. So it basically stores employee information in an IT company. Below is an excel ark with current data from the employees table:

| employee\_id | employment\_type | firstname | middlename | lastname | hire\_date |
| :---- | :---- | :---- | :---- | :---- | ----- |
| 6c4d8219-5e0c-4b1b-8296-014b6694b3b9 | DEV | Peter |  | Hansen | 2025-04-09 |
| cb56d503-cd79-44c3-bc4b-3e96b26f8a45 | DEV | RAJ | PATHAK | KUMAR | 2025-04-08 |
| ef57c0e7-d4b3-4b28-8001-59480ff5772e | DEV | RAJ | PATHAK | KUMAR | 2025-04-08 |

I have only made 1 table, because I think database design is beyond the scope of the assignment. Instead I have focused on choosing the right database technology.

**How I implemented solution**

It is not possible to achieve certain things through the GUI of the  website, but Neon tech has a SQL section, where you can run SQL to work with the database and I utilized both ways. 

To control access to the data at the most granular level I wanted to create a user that could only see the hire\_date column. To achieve this I created a view on top of the employees table that only shows the hire\_date column and assigned it to a user, created for the purpose.

**Why PostgreSQL?**

To control access level at the most fine grained level, my research suggested that Oracle and PostgreSQL DBMS’s are the best choices here. There are other databases that also have the desired functionality, but they are not as popular as the 2 mentioned, which means there is a larger community behind them and better support options. 

When deciding which one to use between them, since Oracle database is for enterprise applications and has more features, it would take longer to learn and implement. The documentation is also a bit difficult to use, in my personal opinion. 

PostgreSQL is more lightweight in comparison and hence easier and quicker to learn, thus making it more suitable for this case. 

