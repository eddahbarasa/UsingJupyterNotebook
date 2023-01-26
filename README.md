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

## Mission 4: Creating and reading records in a MySQL database using Python

The tables created in the database are:
* A table called Menu that stores menu data
*	A table called MenuItems that stores data on menu items
*	A table called Orders that stores data on customer orders 
*	A table called Bookings that stores data on customer bookings

I now need to populate these tables with relevant data and read the data once the records have been inserted into the database.

#### Task 1: Insert and read the data in all the tables
Insert data in all four tables in the little_lemon database using Python
Use the SELECT query to check the output and ensure that each insert query has been executed 

###### Inserting data into Bookings table

![image](https://user-images.githubusercontent.com/106580846/214827516-0c25438b-c507-4f15-b9ee-a326ba7cd2ae.png)

###### Viewing data in Bookings table

![image](https://user-images.githubusercontent.com/106580846/214827701-38011b13-c4e8-42ca-9aae-f8e576b1da24.png)

###### Inserting data into MenuItems table
![image](https://user-images.githubusercontent.com/106580846/214827802-fbfe5cff-94c2-4d65-a99d-ea86e9d738b4.png)
![image](https://user-images.githubusercontent.com/106580846/214827837-241e7e6b-7720-4b90-aa7e-9ff6e0bc13ea.png)

###### Viewing data from MenuItems table
![image](https://user-images.githubusercontent.com/106580846/214827949-8ce3a9c2-8cc0-4c2e-b2d8-78d6e8220e3a.png)
![image](https://user-images.githubusercontent.com/106580846/214827964-05b22e8c-1aa6-4226-b4a8-a7841924cc6d.png)

###### Inserting data into Menus table
![image](https://user-images.githubusercontent.com/106580846/214828038-99542c8d-477c-49d8-9423-2c68dc7f45f7.png)

###### Viewing data in Menus table
![image](https://user-images.githubusercontent.com/106580846/214828143-f07bded4-ec66-4d10-9b9c-402cce603a36.png)
![image](https://user-images.githubusercontent.com/106580846/214828160-f6bb2ae0-753a-4f69-aff2-c71ed6a436e0.png)

###### Inserting data into Orders table
![image](https://user-images.githubusercontent.com/106580846/214828250-e01a4e1d-d706-4f5e-bc86-b0b746706a8e.png)

###### Viewing data in Orders table 
![image](https://user-images.githubusercontent.com/106580846/214828291-9d387682-9686-43ae-a03b-a4465cf63278.png)

#### Task 2: Retrieving records

Retrieve the following data for each guest:
*	Guest first and last names.
*	The table number assigned to each guest.
Use a for loop to iterate over the results that you fetch using the cursor

![image](https://user-images.githubusercontent.com/106580846/214828490-4256a818-2559-49d7-a72e-d0a9de547313.png)

#### Task 3: Retrieving the first 3 records only
The  queries are returning large volumes of data. I need to find a way to return the data in smaller, more manageable chunks. 
Return just the first three items from the menu. 

###### Method 1: Using fetchmany()

![image](https://user-images.githubusercontent.com/106580846/214828657-f641892b-e2c4-4bc0-a8d8-4b0d11fceba4.png)

to retrieve the rest of the records..........

![image](https://user-images.githubusercontent.com/106580846/214828693-c2c2f553-5dfb-4df8-a4eb-b47aecee05f8.png)

###### Method 2: Setting a limit of 3 in the sql query
![image](https://user-images.githubusercontent.com/106580846/214828795-0e3d37e5-4e27-4983-a29b-b588aabce22a.png)

## Mission 5: Updating and deleting records in a MySQL database using Python

Update the records of customers in the database and delete records related to menu items. 

#### Task 1: Updating one column a guest’s Bookings Record
Change the guest Diana Pinto’s booking to table 10 in the MySQL database using an SQL UPDATE statement in Python.

![crud 1](https://user-images.githubusercontent.com/106580846/214831603-2c4e8ac2-b8e4-4db9-b7d7-dc33dc1a68fb.png)

#### Task 3: Updating two columns in guest’s Bookings record
There has been a conflict with two bookings. To resolve the conflict, you need to update the record for the guest Joakim Iversen.
Update Joakim’s booking in the MySQL database using Python as follows:
*	Change the guest’s table number to 11.
*	Change the EmployeeID of the guest’s waiter to 6.

![crud 2](https://user-images.githubusercontent.com/106580846/214831799-55796ecb-1991-4bc1-8dd2-fd3a92c80e5f.png)

#### Task 4: Deleting a record

The restaurant didn’t receive their regular supply of ingredients today. This means that they can’t provide any Greek cuisine for their guests. They need to delete all Greek cuisine from their menu until the supply of ingredients is restored. 
![crud 3](https://user-images.githubusercontent.com/106580846/214831905-b7408995-4e23-420b-844f-32ef6471245d.png)

## Mission 6: Filtering and sorting data in a MySQL database using Python





