# amanRaj_Lab1_Python
**An E-commerce website manages its data in the form of various tables.**

**- Problem Statement **
- Load required libraries
- Connect to DB using mysql-connector-python package
- Create database named **`e_commerce`**
- Create tables and insert data into tables as specified in the question
- Read all the questions and write sql queries to meet the objective.

You need to create a Database called **`e_commerce`** and various tables in it. The tables needed and attributes which need to be in every table are given before hand. All you have to do is create tables with data in it and answer some of the questions that follows.

### Q1. Create tables for supplier, customer, category, product, productDetails, order, rating to store the data for the E-commerce with the schema definition given below.


- **`supplier`**(SUPP_ID int primary key, SUPP_NAME varchar(50), SUPP_CITY varchar(50), SUPP_PHONE varchar(10))


- **`customer`** (CUS_ID INT NOT NULL, CUS_NAME VARCHAR(20) NULL DEFAULT NULL, CUS_PHONE VARCHAR(10), CUS_CITY varchar(30) ,CUS_GENDER CHAR,PRIMARY KEY (CUS_ID))


- **`category`** (CAT_ID INT NOT NULL, CAT_NAME VARCHAR(20) NULL DEFAULT NULL,PRIMARY KEY (CAT_ID))


- **`product`** (PRO_ID INT NOT NULL, PRO_NAME VARCHAR(20) NULL DEFAULT NULL, PRO_DESC VARCHAR(60) NULL DEFAULT NULL, CAT_ID INT NOT NULL,PRIMARY KEY (PRO_ID),FOREIGN KEY (CAT_ID) REFERENCES CATEGORY (CAT_ID))


- **`product_details`** (PROD_ID INT NOT NULL, PRO_ID INT NOT NULL, SUPP_ID INT NOT NULL, PROD_PRICE INT NOT NULL,
  PRIMARY KEY (PROD_ID),FOREIGN KEY (PRO_ID) REFERENCES PRODUCT (PRO_ID), FOREIGN KEY (SUPP_ID) REFERENCES SUPPLIER(SUPP_ID))
  
  
- **`order`** (ORD_ID INT NOT NULL, ORD_AMOUNT INT NOT NULL, ORD_DATE DATE, CUS_ID INT NOT NULL, PROD_ID INT NOT NULL,PRIMARY KEY (ORD_ID),FOREIGN KEY (CUS_ID) REFERENCES CUSTOMER(CUS_ID),FOREIGN KEY (PROD_ID) REFERENCES PRODUCT_DETAILS(PROD_ID))


- **`rating`** (RAT_ID INT NOT NULL, CUS_ID INT NOT NULL, SUPP_ID INT NOT NULL, RAT_RATSTARS INT NOT NULL,PRIMARY KEY (RAT_ID),FOREIGN KEY (SUPP_ID) REFERENCES SUPPLIER (SUPP_ID),FOREIGN KEY (CUS_ID) REFERENCES CUSTOMER(CUS_ID))

- ### Q2. Insert the following data in the table created above
#### `Note:` If you are getting any error while inserting the data into tables, Kindly close the connection and reconnect

#### Table:  supplier
| SUPP_ID | SUPP_NAME | SUPP_CITY | SUPP_PHONE |
| --- | --- | --- | --- | 
| 1 | Rajesh Retails | Delhi | 1234567890 |
| 2 | Appario Ltd. | Mumbai | 258963147032 | 
| 3 | Knome products | Bangalore | 9785462315 |
| 4 | Bansal Retails | Kochi | 8975463285 |
| 5 | Mittal Ltd. | Lucknow | 7898456532 |

### Q3) Display the number of the customer group by their genders who have placed any order of amount greater than or equal to Rs.3000.

### Q4) Display all the order along with product name ordered by a customer having Customer_Id=2;

### Q5) Display the Supplier details who can supply more than one product.

### Q6) Find the category of the product whose order amount is minimum.

### Q7) Display the Id and Name of the Product ordered after “2021-10-05”.

### Q8) Print the top 3 supplier name and id and rating on the basis of their rating along with the customer name who has given the rating.

### Q9) Display customer name and gender whose names start or end with character 'A'.

### Q10) Display the total order amount of the male customers.

### Q11) Display all the Customers left outer join with  the orders.


