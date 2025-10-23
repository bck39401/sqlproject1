
# SQL Project 1 | Group 1
Members: Ben Kim, Jackson Avey, Christian Hertzig, Success Onichabor, Drew Vajda
[Insert Scenario here]





## Data Model
[Insert Data Model and Description here]

## Data Dictionary
Table: Customer
customer_id
INT
Primary Key. Unique ID for each customer
first_name
VARCHAR(45)
Customer’s First Name
last_name
VARCHAR(45)
Customer’s Last Name
phone_num
INT
Customer’s phone number
email
VARCHAR(45)
Customer’s email address
street_name
VARCHAR(45)
Customer’s street address
city
VARCHAR(45)
Customer’s city
state
VARCHAR(45)
Customer’s state
zip_code
INT
Customer’s ZIP or postal code


Table: orders
orders_id
INT
Primary Key. Unique ID for each order.
order_status
VARCHAR(45)
Current status of the order (e.g., Pending, Shipped)
order_date
DATETIME
Date the order was placed.
required_date
DATETIME
Date the order is required to be fulfilled
shipped_date
DATETIME
Date the order was shipped
customer_customer_id
INT
Foreign Key referencing customer(customer_id). Identifies which customer placed the order.



## Ten Queries
[Insert Queries and their Descriptions here]

## Database Information
[Insert Database Info Table here]
