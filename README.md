# UsingJupyterNotebook
Come along my journey as I utilize Jupyter Notebook to make use of python programming language to work with a MySQL backend database.

## Mission 1: Establish a MySQL/Python connection

A company is developing a Python-based application that needs to use MySQL in the back end so that they can store day-to-day data 
Establish a connection between Python and the MySQL server so that they can access and communicate with the database using Python.

**Step** **1**: Install the mysql-connector-python package to be able to run the code

![connector instal](https://user-images.githubusercontent.com/106580846/213401738-c5a13830-435d-4be0-9ebf-9731ffc5d959.png)

**Step** **2**: Import the MySQL connector library using the alias "connector" and create a variable that I will call "connection".
Then use the variable to store an instance of the connection made with the database using the connector module. The parameters I will use for this connection are user and password, haven't created a database yet.  

![connector 2](https://user-images.githubusercontent.com/106580846/213402543-54103e29-9762-43df-8923-6639846a27f5.png)

## Mission 2: Using try/except blocks

To ensure that there are no connection issues when connecting with MySQL database I use try/except blocks when making the connection

**Step** **1**: Import an instance of MySQL connector using the alias connector.

**Step** **2**: Open a try block and store an instance of the connection and an except block to print a meaningful message if the connection has an issue. Then intentionally enter a wrong user or password to view the output. 

![connector 3](https://user-images.githubusercontent.com/106580846/213406870-79781113-26d0-4a4c-8d36-d09507d35b62.png)

## Mission 3:Identify connection issues

To identify the specific reason for any connection issues and display the error code along with the error message in the following situations: 
* When the database does not exist.
* When a wrong username or password is entered.










