Microsoft Windows [Version 10.0.22000.2538]
(c) Microsoft Corporation. All rights reserved.

C:\Users\ADMIN>mysql -u root -p
Enter password: ***********
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 15
Server version: 8.0.44 MySQL Community Server - GPL

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> USE sales_db;
Database changed
mysql> DROP TABLE IF EXISTS sales;
Query OK, 0 rows affected (0.07 sec)

mysql>
mysql> CREATE TABLE sales (
    ->   Row_ID INT,
    ->   Order_ID VARCHAR(50),
    ->   Order_Date DATE NULL,
    ->   Ship_Date DATE NULL,
    ->   Ship_Mode VARCHAR(50),
    ->   Customer_ID VARCHAR(50),
    ->   Customer_Name VARCHAR(100),
    ->   Segment VARCHAR(50),
    ->   Country VARCHAR(50),
    ->   City VARCHAR(50),
    ->   State VARCHAR(50),
    ->   Postal_Code INT NULL,
    ->   Region VARCHAR(50),
    ->   Product_ID VARCHAR(50),
    ->   Category VARCHAR(50),
    ->   Sub_Category VARCHAR(50),
    ->   Product_Name TEXT,
    ->   Sales DECIMAL(10,2) NULL
    -> );
Query OK, 0 rows affected (0.02 sec)

mysql> LOAD DATA INFILE 'C:/ProgramData/MySQL/MySQL Server 8.0/Uploads/sales_data_cleaned.csv'
    -> INTO TABLE sales
    -> FIELDS TERMINATED BY ','
    -> ENCLOSED BY '"'
    -> LINES TERMINATED BY '\n'
    -> IGNORE 1 ROWS
    -> (@Row_ID, @Order_ID, @Order_Date, @Ship_Date, @Ship_Mode, @Customer_ID, @Customer_Name, @Segment,
    ->  @Country, @City, @State, @Postal_Code, @Region, @Product_ID, @Category, @Sub_Category, @Product_Name, @Sales)
    -> SET
    ->  Row_ID = NULLIF(@Row_ID,''),
    ->  Order_ID = @Order_ID,
    ->  Order_Date = NULLIF(@Order_Date,''),
    ->  Ship_Date = NULLIF(@Ship_Date,''),
    ->  Ship_Mode = @Ship_Mode,
    ->  Customer_ID = @Customer_ID,
    ->  Customer_Name = @Customer_Name,
    ->  Segment = @Segment,
    ->  Country = @Country,
    ->  City = @City,
    ->  State = @State,
    ->  Postal_Code = NULLIF(@Postal_Code,''),
    ->  Region = @Region,
    ->  Product_ID = @Product_ID,
    ->  Category = @Category,
    ->  Sub_Category = @Sub_Category,
    ->  Product_Name = @Product_Name,
    ->  Sales = NULLIF(@Sales,'');
Query OK, 9800 rows affected, 3931 warnings (0.42 sec)
Records: 9800  Deleted: 0  Skipped: 0  Warnings: 3931

mysql> SELECT * FROM sales LIMIT 5;
+--------+----------------+------------+------------+----------------+-------------+-----------------+-----------+---------------+-----------------+------------+-------------+--------+-----------------+-----------------+--------------+-------------------------------------------------------------+--------+
| Row_ID | Order_ID       | Order_Date | Ship_Date  | Ship_Mode      | Customer_ID | Customer_Name   | Segment   | Country       | City            | State      | Postal_Code | Region | Product_ID      | Category        | Sub_Category | Product_Name                                                | Sales  |
+--------+----------------+------------+------------+----------------+-------------+-----------------+-----------+---------------+-----------------+------------+-------------+--------+-----------------+-----------------+--------------+-------------------------------------------------------------+--------+
|      1 | CA-2017-152156 | 2017-08-11 | 2017-11-11 | Second Class   | CG-12520    | Claire Gute     | Consumer  | United States | Henderson       | Kentucky   |       42420 | South  | FUR-BO-10001798 | Furniture       | Bookcases    | Bush Somerset Collection Bookcase                           | 261.96 |
|      2 | CA-2017-152156 | 2017-08-11 | 2017-11-11 | Second Class   | CG-12520    | Claire Gute     | Consumer  | United States | Henderson       | Kentucky   |       42420 | South  | FUR-CH-10000454 | Furniture       | Chairs       | Hon Deluxe Fabric Upholstered Stacking Chairs, Rounded Back | 731.94 |
|      3 | CA-2017-138688 | 2017-12-06 | NULL       | Second Class   | DV-13045    | Darrin Van Huff | Corporate | United States | Los Angeles     | California |       90036 | West   | OFF-LA-10000240 | Office Supplies | Labels       | Self-Adhesive Address Labels for Typewriters by Universal   |  14.62 |
|      4 | US-2016-108966 | 2016-11-10 | NULL       | Standard Class | SO-20335    | Sean O'Donnell  | Consumer  | United States | Fort Lauderdale | Florida    |       33311 | South  | FUR-TA-10000577 | Furniture       | Tables       | Bretford CR4500 Series Slim Rectangular Table               | 957.58 |
|      5 | US-2016-108966 | 2016-11-10 | NULL       | Standard Class | SO-20335    | Sean O'Donnell  | Consumer  | United States | Fort Lauderdale | Florida    |       33311 | South  | OFF-ST-10000760 | Office Supplies | Storage      | Eldon Fold 'N Roll Cart System                              |  22.37 |
+--------+----------------+------------+------------+----------------+-------------+-----------------+-----------+---------------+-----------------+------------+-------------+--------+-----------------+-----------------+--------------+-------------------------------------------------------------+--------+
5 rows in set (0.00 sec)

mysql> SELECT COUNT(*) FROM sales;
+----------+
| COUNT(*) |
+----------+
|     9800 |
+----------+
1 row in set (0.01 sec)

mysql> DESCRIBE sales;
+---------------+---------------+------+-----+---------+-------+
| Field         | Type          | Null | Key | Default | Extra |
+---------------+---------------+------+-----+---------+-------+
| Row_ID        | int           | YES  |     | NULL    |       |
| Order_ID      | varchar(50)   | YES  |     | NULL    |       |
| Order_Date    | date          | YES  |     | NULL    |       |
| Ship_Date     | date          | YES  |     | NULL    |       |
| Ship_Mode     | varchar(50)   | YES  |     | NULL    |       |
| Customer_ID   | varchar(50)   | YES  |     | NULL    |       |
| Customer_Name | varchar(100)  | YES  |     | NULL    |       |
| Segment       | varchar(50)   | YES  |     | NULL    |       |
| Country       | varchar(50)   | YES  |     | NULL    |       |
| City          | varchar(50)   | YES  |     | NULL    |       |
| State         | varchar(50)   | YES  |     | NULL    |       |
| Postal_Code   | int           | YES  |     | NULL    |       |
| Region        | varchar(50)   | YES  |     | NULL    |       |
| Product_ID    | varchar(50)   | YES  |     | NULL    |       |
| Category      | varchar(50)   | YES  |     | NULL    |       |
| Sub_Category  | varchar(50)   | YES  |     | NULL    |       |
| Product_Name  | text          | YES  |     | NULL    |       |
| Sales         | decimal(10,2) | YES  |     | NULL    |       |
+---------------+---------------+------+-----+---------+-------+
18 rows in set (0.06 sec)

mysql> SELECT SUM(Sales) AS Total_Sales FROM sales;
+-------------+
| Total_Sales |
+-------------+
|  2261536.97 |
+-------------+
1 row in set (0.06 sec)

mysql> SELECT Region, SUM(Sales) AS Total_Sales
    -> FROM sales
    -> GROUP BY Region
    -> ORDER BY Total_Sales DESC;
+---------+-------------+
| Region  | Total_Sales |
+---------+-------------+
| West    |   710219.77 |
| East    |   669518.85 |
| Central |   492646.90 |
| South   |   389151.45 |
+---------+-------------+
4 rows in set (0.08 sec)

mysql> SELECT Category, SUM(Sales) AS Total_Sales
    -> FROM sales
    -> GROUP BY Category
    -> ORDER BY Total_Sales DESC;
+-----------------+-------------+
| Category        | Total_Sales |
+-----------------+-------------+
| Technology      |   827455.94 |
| Furniture       |   728658.75 |
| Office Supplies |   705422.28 |
+-----------------+-------------+
3 rows in set (0.01 sec)

mysql> SELECT DATE_FORMAT(Order_Date,'%Y-%m') AS Month, SUM(Sales) AS Total_Sales
    -> FROM sales
    -> GROUP BY Month
    -> ORDER BY Month;
+---------+-------------+
| Month   | Total_Sales |
+---------+-------------+
| NULL    |  1389173.96 |
| 2015-01 |    19546.17 |
| 2015-02 |    11678.99 |
| 2015-03 |     6716.05 |
| 2015-04 |    12455.48 |
| 2015-05 |    15165.07 |
| 2015-06 |    11884.17 |
| 2015-07 |    10075.75 |
| 2015-08 |    26797.78 |
| 2015-09 |    17158.91 |
| 2015-10 |    10112.63 |
| 2015-11 |    18349.73 |
| 2015-12 |    17045.85 |
| 2016-01 |    17701.67 |
| 2016-02 |    13018.30 |
| 2016-03 |    12207.41 |
| 2016-04 |    11963.70 |
| 2016-05 |    10483.46 |
| 2016-06 |    13026.65 |
| 2016-07 |    10706.74 |
| 2016-08 |    22782.57 |
| 2016-09 |    16484.90 |
| 2016-10 |    12293.03 |
| 2016-11 |    12139.05 |
| 2016-12 |     9761.34 |
| 2017-01 |    26342.54 |
| 2017-02 |    42967.91 |
| 2017-03 |    25982.30 |
| 2017-04 |    19472.16 |
| 2017-05 |    22649.41 |
| 2017-06 |    14050.12 |
| 2017-07 |    16501.01 |
| 2017-08 |    24156.31 |
| 2017-09 |     9789.69 |
| 2017-10 |    22599.79 |
| 2017-11 |    20378.24 |
| 2017-12 |    21365.10 |
| 2018-01 |    27367.59 |
| 2018-02 |    36285.94 |
| 2018-03 |    26882.95 |
| 2018-04 |    21203.57 |
| 2018-05 |    15979.16 |
| 2018-06 |    12138.16 |
| 2018-07 |    25110.45 |
| 2018-08 |    26823.71 |
| 2018-09 |    23148.90 |
| 2018-10 |    17558.32 |
| 2018-11 |    17407.25 |
| 2018-12 |    16647.03 |
+---------+-------------+
49 rows in set (0.06 sec)

mysql>
