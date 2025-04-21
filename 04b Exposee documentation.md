Assignment 04b   
Exposee: Muhammad Ali Khan  
Integrator: Shero Shvan

**Documentation for PostgreSQL database**

**Required installation**

PostgreSQL

- Download installer for PostgreSQL 17.4 and relevant OS here(if you can’t click on link, then right click and choose ‘Åben link’):  
    
    
   [EDB: Open-Source, Enterprise Postgres Database Management](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)   
    
    
- Run file and after installation has been completed, the screen below will appear. Make sure that the checkbox(launch stack builder at exit) is not checked and finish installation   
- To use the cli tool called psql, locate bin folder, path for windows is like this: 

  C:\\Program Files\\PostgreSQL\\17\\bin

Add this to your system environment variable called ‘Path’ on Windows.

**Connect to database**

There are 4 users with different privileges. Below you can see information listed, necessary to connect with database, which is hosted on neon.tech:

Host: ep-crimson-king-a2d0puri-pooler.eu-central-1.aws.neon.tech  
Port: 5432  
Database name: it\_firm  
Schema: personel  
Table: employees  
View: vw\_employees\_limited  
Password: ThunderChicken2025  
Usernames:

1) pg\_database\_owner   
2) readonly  
3) insert\_only  
4) readonly\_limited

First user has admin rights and readonly can only do select statements and insert\_only can only create rows. The password is the same for all users.

The last user(*readonly\_limited*) can only see the hire dates of the employees and for this, a view is made on top of the *employees* table, called vw\_employees\_limited. See example with view later in documentation. 

Open a terminal and run the following psql command:

psql \-h ep-crimson-king-a2d0puri-pooler.eu-central-1.aws.neon.tech \-p 5432 \-U readonly \-d it\_firm \-W

Flag explanation:

\-h the address of host  
\-p the port number, where database is running  
\-U username   
\-d database name  
\-W makes cli prompt for password

To logout press ctrl \+ c and try to login with the other users. Trying to use privileges a user does not have, will give an error saying access denied.

Once logged in, you can try out this command:

SELECT \* FROM personel.employees;

Creating a row ( for insert\_only user fx)

INSERT INTO personel.employees (employment\_type, firstname, middlename, lastname, hire\_date) VALUES ('DEV', 'RAJ', 'PATHAK', 'KUMAR', '2025-04-08');

If you login with *readonly\_limited* you can attempt to use a SELECT statement with employees table, but it wont work, because this user is only supposed to have access to 1 column in the table and this is where the view made for this purpose comes in.

The command below should display all hire dates:

SELECT \* FROM vw\_employees\_limited;

