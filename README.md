# UsingJupyterNotebook
Come along my journey as I utilize Jupyter Notebook to make use of python programming language to work with a MySQL backend database.

## Mission 1: Establish a MySQL/Python connection
#### Task 1
A company is developing a Python-based application that needs to use MySQL in the back end so that they can store day-to-day data 
Establish a connection between Python and the MySQL server so that they can access and communicate with the database using Python.

**Step 1:** Install the mysql-connector-python package to be able to run the code

![connector instal](https://user-images.githubusercontent.com/106580846/213401738-c5a13830-435d-4be0-9ebf-9731ffc5d959.png)

**Step 2:** Import the MySQL connector library using the alias "connector" and create a variable that I will call "connection".
Then use the variable to store an instance of the connection made with the database using the connector module. The parameters I will use for this connection are user and password, haven't created a database yet.  

![connector 2](https://user-images.githubusercontent.com/106580846/213402543-54103e29-9762-43df-8923-6639846a27f5.png)

#### Task 2: Using try/except blocks

To ensure that there are no connection issues when connecting with MySQL database I use try/except blocks when making the connection

**Step 1:** Import an instance of MySQL connector using the alias connector.

**Step 2:** Open a try block and store an instance of the connection and an except block to print a meaningful message if the connection has an issue. Then intentionally enter a wrong user or password to view the output. 

![connector 3](https://user-images.githubusercontent.com/106580846/213406870-79781113-26d0-4a4c-8d36-d09507d35b62.png)

#### Task 3: Identify connection issues

To identify the specific reason for any connection issues and display the error code along with the error message in the following situations: 
* When the database does not exist.
* When a wrong username or password is entered.
* 
**Step 1:** Import an instance of MySQL connector using the alias connector.

**Step 2:** Then open a try block and  and store an instance of the connection and in the except block I will use the Error class from mysql.connector to get the error code and message

![connector 4](https://user-images.githubusercontent.com/106580846/213413219-becbf7b2-bf61-4845-8afc-b4e5d8dc2868.png)

#### Task 4: Closing the connection
 
  ![connector 5](https://user-images.githubusercontent.com/106580846/213413397-45f80969-202d-48c2-9fef-8fb7f4c7879c.png)
  
 ## Mission 2: Creating a table structure in a MySQL database using Python

The company needs to create a database that can hold the following tables
* A table called Menu that stores menu data 
*	A table called MenuItems that stores data on menu items 
* A table called Orders that stores data on customer orders 
*	A table called Bookings that stores data on customer bookings 

**Step 1:** Create the database to hold the tables call it "little_lemon".

![table 1](https://user-images.githubusercontent.com/106580846/213430948-57ee56de-7dfe-4e86-a2c8-de5791712ad5.png)

**Step 2:** Set the newly created database little_lemon for use and confirm that the database is available for use by using connection.database. 

![table 0](https://user-images.githubusercontent.com/106580846/213431060-2c74efa3-f926-4eb6-bc0e-adc80c35288b.png)

**Step 2:** Create a MenuItems table and use the command “show tables” to confirm that the table has been created.

![table 2](https://user-images.githubusercontent.com/106580846/213431872-f1bff736-95d7-4251-9721-7abdb2843e4a.png)

**Step 3:** Create a Menus table and use the command “show tables” to confirm that the table has been created.

![table 4](https://user-images.githubusercontent.com/106580846/213432228-77719e9f-1b03-41dd-931a-3bfdb36a3251.png)

**Step 4:** Create a Bookings table and use the command “show tables” to confirm that the table has been created.

![table 5](https://user-images.githubusercontent.com/106580846/213432374-425491d7-bbf6-4dc6-83f4-4169beab156f.png)

**Step 5:** Create an Orders table and use the command “show tables” to confirm that the table has been created.

![table 6](https://user-images.githubusercontent.com/106580846/213432703-95e5cfa8-4a20-4a82-9df7-f682078c68fd.png)

## Mission 3: Working with cursors

I need to perform some basic tasks on the database such as setting up the database and checking the names of the tables in the database. Hence, I have established a connection with the MySQL database using Python. 

#### Task 1: Find out what tables currently exist in the database. 

**Step 1:** Set the database little_lemon in use. 
**Step 2:** Create a cursor object and execute SHOW TABLES to retrieve the names of the tables in the database.
**Step 3:** Fetch all the names in a variable and use the for loop to print the output.   

![cursor 1](https://user-images.githubusercontent.com/106580846/213447417-05635b20-11ee-4f6b-a122-8b09ca12a33f.png)

#### Task 2: Standard Vs Buffered Cursor
Run a test between the standard and the buffered cursor to check what type of cursor will work for the situation given below:

Create a cursor
* Execute USE little_lemon
* Execute SELECT * FROM Bookings
* Execute SELECT * FROM Orders

###### Standard Cursor

![cursor 2](https://user-images.githubusercontent.com/106580846/213452130-9c8f3e62-f568-4499-a99e-e6415da95045.png)

###### Buffered Cursor

![cursor 3](https://user-images.githubusercontent.com/106580846/213452202-d8238515-5ac4-4ac3-8a09-66ec642826e1.png)

#### Task 3: Using a Dictionary cursor

Create a cursor with the argument [dictionary = True] and retrieve the names of all the tables in the form of a dictionary object where the name of the tables is a value, and the database name is a key. 

![cursor 5](https://user-images.githubusercontent.com/106580846/213453310-a23fde23-a9ae-4ced-b5bb-50a702018a64.png)









 











