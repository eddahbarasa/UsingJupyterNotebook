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

The restaurant needs to filter and sort the data in their MySQL database using Python to complete the following tasks:
*	Determine which waiter is serving which guest,
*	Identify all guests who paid a bill amount above a certain threshold,
*	List all starters above a certain price and order with the price.

#### Task 1: Filtering
Query the database to find out how many bookings they have today for table number 12. Find the names of the guests booked for table 12 and who their servers are. 
The output should include:
*	TableNo
*	GuestFirstName
*	GuestLastName
*	EmployeeID
*	
![sorting 1](https://user-images.githubusercontent.com/106580846/214839482-0a08e4e2-8e51-4648-85f4-dfb364bca07f.png)

#### Task 2: Filtering & sorting
We want to send a coupon to all guests who spent more than $40 at the restaurant today. Filter and sort the records of all guests who qualify for the coupons.

![sorting 2](https://user-images.githubusercontent.com/106580846/214839580-e9589bba-e9d6-487d-a9e9-7b4880149823.png)

#### Task 3: filtering & sorting
A guest wants to know the price of today’s starters and desserts. Create a query that extracts the prices and details of starters and dessert options only from the MenuItems table. Order these prices from lower to higher.

![sorting 3](https://user-images.githubusercontent.com/106580846/214839653-727e9ba1-94e5-45b7-9547-c97530df57be.png)

## Mission 7: Performing JOIN operations in MySQL databases using Python

The restaurant needs to carry out the following tasks with their datasets:
*	Determine the final bill amount for each customer who attended the restaurant today 
*	Identify the type of cuisine that each item in their menu belongs to

#### Task 1: Performing inner join
The restaurant needs the following information for each of the items on their menu:
* The name of each item in the menu
*	Each menu item’s type
*	Each menu item’s cuisine
*	The price of each item in the menu

![join 1](https://user-images.githubusercontent.com/106580846/214841058-7dfa9468-2b1d-4fe8-aa40-98c8f2cb98b4.png)

#### Task 2: Performing a left join
The restaurant noticed that there are several menu items in the MenuItems records that are absent from the Menus table. Identify the items that are present in the MenuItems records but absent from the Menus table by using a LEFT JOIN operation on the MenuItems table.

![join 2](https://user-images.githubusercontent.com/106580846/214841395-3bf71ac2-2b8c-459a-99ff-6002747edc03.png)

#### Task 3: Performing inner join
The restaurant needs to retrieve the following information from the Bookings and the Orders tables in their MySQL database using Python:
*	Booking ID
*	Table number
*	Guest first name
* Bill amount

![join 3](https://user-images.githubusercontent.com/106580846/214841898-efb99426-b73c-4511-8392-33b029932305.png)

## Mission 8: Utilizing MySQL functions with Python

There are several occasions where the restaurant needs to perform routine operations, some of them include total sales, the total number of guests, the number of items in each cuisine, the full name of the guests, and so on. 

#### Task 1:

Along with the booking ID, little lemon needs to add the full name of the guests in upper case on their invoices. Help little lemon to extract the data in the required format.

![function 1](https://user-images.githubusercontent.com/106580846/215055520-e5da3e24-0737-4ad8-b0d4-0903c20da8f6.png)

#### Task 2:
Little lemon needs to know the following statistics at closing:
*	Number of bookings
*	Total sale
*	Average sale

![todays](https://user-images.githubusercontent.com/106580846/215055944-e47ac8e5-7f76-4948-90a9-7c80caae7793.png)

#### Task 3:

Little lemon needs to know the number of bookings for each table. Print the table number and the number of bookings for each table. 

![function 3](https://user-images.githubusercontent.com/106580846/215056090-76462cca-1ac5-4b26-81b8-796462e1fcc8.png)

#### Task 4:

Little lemon wants to create three arrival slots for the guests based on the booking hour:
*	Late afternoon: for hours 15 and 16 
*	Evening: for hours 17 and 18
*	Night: for hours 19 and 20

Display the booking ID, guest name, and arrival slot on the kitchen screen so that the staff can plan accordingly. 
Target GuestFirstName and GuestLastName columns and combine them to get Guest_Name. Use the MySQL CASE function and create Arrival_slot for each guest

![functions 4](https://user-images.githubusercontent.com/106580846/215056215-d29348ed-a6c7-4972-a1ef-d84f1828d747.png)

## Mission 9: Working with date and time functions in Python

The restaurant needs to schedule its staff’s duties according to the restaurant’s peak hours. They also want to display the guest’s name and their expected arrival time on the kitchen screen to keep the staff informed. These and several other similar tasks, such as changing the booking time, require working with the date and time column. 

#### Task 1:
Retrieve the number of bookings in each hour so that we can schedule staff’s duties accordingly. 

###### Steps:
* Step 1: Target the BookingID and BookingSlot columns from the Bookings table. 
* Step 2: Extract the hour from the BookingSlot column and count the bookings in each hour.
* Step 3: Group and order the data by hour. 

![datetime 1](https://user-images.githubusercontent.com/106580846/215057763-28be6cf4-73e3-466e-b5d4-1e930ccc2920.png)

#### Task 2:
Little Lemon needs to display the following information for their staff:
*	Each guest’s table number
*	Each guest’s full name
*	The expected arrival time in hours and minutes of each guest (e.g., 15 hours and 0 mins).
 
###### Steps:
*	Target TableNo, GuestFirstName, GuestLastName and BookingSlot columns in the Bookings table. 
*	Order the data by BookingSlot. 
*	Use Python’s datetime module to extract hours and minutes using the strptime function when printing the record. 

![datetime 2](https://user-images.githubusercontent.com/106580846/215058020-b999956f-fb10-4e12-8b96-2b44d32d01af.png)

#### Task 3:
A guest with booking ID 2 and table number 12 wants to change their arrival time by one hour from 7pm to 8pm.

###### Steps:
*	Target BookingID, TableNo and BookingSlot columns in the Bookings table. 
*	Add one hour in the BookingSlot. 
*	Use the WHERE clause on TableNo and BookingID columns. 

![datetime 3](https://user-images.githubusercontent.com/106580846/215058220-3bfa6777-d103-442c-9910-6255ff984229.png)

## Mission 10: Stored procedures using python

The restaurant needs to perform some tasks on daily basis, and they involve extracting data from one or more tables. 

The tasks include:
*	Finding the guest with maximum spending, 
*	Retrieving the bookings for no arrival, 
*	Displaying the order status to the guests. 

To keep consistency during the data retrieval process, the restaurant  wants to implement the required tasks using stored procedures. 

#### Task 1:

We are running a marketing campaign this month. We need to issue a discount coupon to the top spender on daily basis. Create a stored procedure TopSpender that can retrieve the following, the booking ID, guest’s full name, and the bill amount of the top spender at closing. Call the procedure and print the results. 
###### Steps:
*	Target BookingID, GuestFirstName, GuestLastName and BillAmount columns from the Bookings and the Orders tables. 
*	Use the concatenation function to get the guest’s full name. 
*	Join the two tables and retrieve the top spender. 
*	Create a stored procedure
*	Call it by its name using python and print the results.

![proc 1](https://user-images.githubusercontent.com/106580846/215060851-793c65cf-fd5e-4ec8-ba07-094c52edc623.png)

#### Task 2:
Retrieve all those bookings where the guests did not appear today. Use NoArrival as a name for your stored procedure. 

###### Steps:
*	Target the Orders and the Bookings tables
*	Join them on BookingID and retrieve the records with a NULL value in the bill amount. 
*	Create a stored procedure, 
*	Call it by its name using Python and print the results.  

![proc 2](https://user-images.githubusercontent.com/106580846/215061142-3ce49115-832e-4f02-b6a7-027346026830.png)

#### Task 3:
It is very important for the restaurant to keep track of the status of each guest’s order and display it on the screen to keep their guests informed. 
This is how they categorize the orders:

*If not assigned to any employee, the status is In Queue*

*If assigned to the employees with IDs 4 and 5, the status is Preparing Order*

*If assigned to the employees with IDs 1, 2, and 3, the status is Order Served*

Create a stored procedure named OrderStatus for the above task and call the procedure.

##### Steps:
*	Target EmployeeID column in the Bookings table
*	Use the CASE function in your stored procedure query
*	Create a stored procedure 
*	Call it by its name using python and print the results.

![proc 3](https://user-images.githubusercontent.com/106580846/215061709-e7c6e583-65e5-4e0c-ae25-4797af300c36.png)![proc 3 results](https://user-images.githubusercontent.com/106580846/215061751-2ccb255c-4c5a-4a90-88db-a6472b6c1bac.png)

## Mission 11: Working with connection pools

The restauranat's guests need to access the database for any booking or inquiry, for example, reading the menu. We, therefore, need to establish a connection between the Python and MySQL databases for every operation.  

Establishing a connection every time is resource intensive and it is affecting the performance of the application. To improve the performance of the application, we need to establish a pool of database connections to facilitate the guests’ inquiries to the database.

#### Task 1:
Create a database connection pool with three connections available for the users to connect to the database with. Import MySQLConnectionPool class and pass the following arguments:
* pool_name = “ll_pool_a”
* pool_size = 3
*	**dbconfig

###### Steps:
*	Use the actual name of the database together with authenticated username and password in the above configuration. 
*	Use the Error class from mysql.connector to handle a possible error in an instance where the wrong parameters are passed on the database configuration.
* Use try-except block from Python to implement the error handling. 
* Once the connection pool is created, use the print statements to display the name of the pool and the number of connections in it. 

![connection 1](https://user-images.githubusercontent.com/106580846/215071463-63166e6d-558f-4338-b340-9203a7488365.png)

#### Task 2:
Get a connection from the database connection pool that you have created in the first task and retrieve the following columns from the Bookings table:
BookingID GuestFirstName GuestLastName

Retrieve the required columns and put the connection back into the pool after you have completed the task.

![connection 2 a](https://user-images.githubusercontent.com/106580846/215071646-c32f6b8a-4b4a-4e27-9dbd-cb7e23cf16a5.png)![connection 2 b](https://user-images.githubusercontent.com/106580846/215071670-133745ea-d6dd-4b07-99bb-1624497d66db.png)![connection 2 c](https://user-images.githubusercontent.com/106580846/215071714-aa2dba1d-4c33-4ac8-873a-d40c174bac2b.png)

#### Task 3:
The following five guests want to connect to the database:

guests = ["Anna", "Marcos", "Diana", "Joakim", "Hiroki"]

You only have three connections in the database connection pool. 
Use the available connection in the pool to connect three guests and then add new connections to the pool to connect the two remaining guests. 

Ensure that all five guests are connected to the database at the same time, by adding more connections to the pool. Use add_connection module from the pool and add a new connection if all existing connections are in use. Use try-except from Python and print the message to inform the user when connected

![connection 3 a](https://user-images.githubusercontent.com/106580846/215072078-f9727741-b1a8-4d29-ba7f-2fa7b0250971.png)
![connection 3 b](https://user-images.githubusercontent.com/106580846/215072095-848ca45d-c131-42fc-81ec-d044d0bbd6af.png)
