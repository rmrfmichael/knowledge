# Installing PostgreSQL

## Linux Ubuntu
The following line is meant for Ubuntu version 16.04 (xenial-xerus). If you are on Ubuntu version 18, replace the word "xenial" with "bionic"
`$ sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' > /etc/apt/sources.list.d/pgdg.list"`

This is for Ubuntu 18
`$ sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ bionic-pgdg main' > /etc/apt/sources.list.d/pgdg.list"`

Once you have one of the above commands -- as in _not_ both commands, you will continue on running the following commands:  
```
$ wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install postgresql-common
$ sudo apt-get install postgresql-9.5 libpq-dev
```  
  
Once the installation is complete, you'll need to create a user for PostgreSQL. Like so:  
Replace (username) with your chosen username. Please don't try to type in a literal "(username)" as your username.  
`$ sudo -u postgres createuser (username) -s`  
  
Now that you have a user for Postgres, you might want to set a password for your account (you do)  
`sudo -u postgres psql`  
  
The above command drops you into the postgres prompt, it is now waiting for postgres commands, not bash/terminal commands.
To set a password for the user account you just created, run the following command:  
`postgres=# \password (the username you used above)`


# Mac OSX

To quickly install PostgreSQL on Mac, simply run: `brew install postgres`.  
If you want a GUI to run SQL and interact with databases, Postico is a great option.  

My recommended approach to installing PostgreSQL is to use the EnterpriseDB installer, which will run by clicking the following link:  
`https://www.enterprisedb.com/thank-you-downloading-postgresql?anid=1256158`  
  
With the above installer, PostgreSQL will come installed with my favorite GUI for SQL queries, pgAdmin 4+
