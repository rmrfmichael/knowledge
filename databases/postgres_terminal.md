# Using PostgreSQL in Bash

To access your databases from the terminal, you need to log into your shell as 'postgres' (the default user) with the following command: 

`$ sudo -u postgres -i`  

You are now using the shell as postgres. Please note that your location in the shell is likely not wherever you logged in from. You should now be in the directory of your PostgreSQL installation. Use the following command to enter the PostgreSQL prompt:  
`$ psql`


From here, you can now enter commands specifically for postgres. These commands only work here, not in terminal, or a programming langauge's REPL. In fact, consider this the REPL for PostgreSQL.  

## PostgreSQL commands

```
$ \du # list all user accounts
$ \?  # list all commands
$ \c [DBNAME] # connect to a database
$ \dt # list all tables (when connected to a database)
$ \q # quit postgres
$ \conninfo # connection information

```  

When connected to a database you can run SQL commands.

## Using SQL (Structured Query Language)

#### Create a table

In order to store information in a database, you need tables to specify different "groups" or "categories" of information.

```
CREATE TABLE users (
    Email varchar(255),
    Name varchar(255),
    id serial);
```

Now that you have a table, you can store information ...  

```
INSERT INTO users (email, name)
VALUES ('johndoe@example.com', 'Jonathan Doe');
```  

You have now stored information in your database. This works like a memory card for a Playstation. You can now return anytime to 
retrieve or edit this information. Here is a SQL command to retrieve information from the database.  

To get all information from a single table
`SELECT * FROM users;`  
  
  
To get a specific column from a table
`SELECT email FROM users;`


We can add tables to this database...  
```
CREATE TABLE articles (
    Title varchar(255),
    Content text,
    id serial,
    user_id integer);
```


