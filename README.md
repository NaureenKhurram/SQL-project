# SQL-project

This project was done completed using PostgreSQL and the data (restaurant takeaway orders) was acquired from kaggle (link to data: https://www.kaggle.com/datasets/henslersoftware/19560-indian-takeaway-orders).

This dataset provided details of takeaway orders for two indian restaurants located in London, UK.  However, the project used data for only one restaurant (containing over 74000 records).

The following steps where taken to  import and structure the data (from a csv file) into the PostgreSQL database:

#### Products Table
1) A table for products/items sold in the restaurant was creating.  This table originally had only two columns a) the name of the item b) price
2) An additional auto-increment primary key column was added to this table.
3) Data was imported into the table using the import wizard (total products 249).

#### Orders Table
1) Originally, the orders table contained the following data: a) order number b) order date c) order time d) Item ordered e) quantity ordered f) price of item g) total products (how many items were ordered in one order)
2) An order table was created with all the above columns.
3) The data from the csv file was imported (74,819 records).
4) An auto-increment primary key column was added to the table.
5) A productID column was added to the table (to link it to the products table).
6) The orders table was updated and productID column was populated from the products table based on the name of the item in both tables.
7) Unnecessary/repeating columns in the orders table were deleted (item ordered, price, total products(this was not required)).
8) A foreign key constraint was added to the orders table linking productID to the product table (thus normalizing the data).

Once the data was structured accurately, analysis such as date range of orders, total per order, total orders per month per year were calculated.
