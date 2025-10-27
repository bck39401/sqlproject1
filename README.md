
# SQL Project 1 | Group 1
Members: Ben Kim, Jackson Avey, Christian Hertzig, Success Onichabor, Drew Vajda

## Scenario
The task at hand is to model and build a relational database for the general operations of a network of bike stores. The central entity in the model is the Store entity, representing each individual location where bikes and related products are sold. Each store manages its stock of products, including details such as quantity, category, and brand. The system also tracks orders placed by customers, consisting of multiple order items tied to specific products. Additionally, employees are associated with each store to manage sales and inventory. The product detail entity provides descriptive information about each item, while the categories and brands entities classify and group products effectively. Our goal is to accurately model these relationships, populate the database with sample data, and perform queries that yield useful insights into sales performance, inventory management, and customer purchasing trends across all stores.





## Data Model
Explanation:
The Bike Store data model captures how products, customers, employees, and orders interact across multiple store locations. It is built around a set of well-defined relationships that mirror the real-world structure of a retail business. At the heart of the design is the Product table, which connects to several entities. Each product belongs to exactly one Brand and one Category, forming two one-to-many relationships from Product to Brand and Category. This means a single brand or category can be associated with many products, but each product can only have one brand and one category. The Product_Detail table is linked to Product through a one-to-one relationship because each product has a unique set of detailed attributes such as model year and list price that apply to that specific item only.
Sales transactions are modeled through the Orders and Order_Item tables. The Orders table connects to Customer in a one-to-many relationship since a single customer can place many orders, but each order belongs to only one customer. Each Order can also have multiple items, leading to a one-to-many relationship between Orders and Order_Item. On the other side, each Order_Item references a single Product, but a product can appear in many order items over time, forming another one-to-many relationship from Order_Item to Product. The Order_Item table serves as an associative entity, enabling a many-to-many conceptual link between Orders and Product while storing key transactional attributes like quantity, discount, and price at the item level.
Inventory and store management are supported by the Stores, Stock, and Employee tables. The Stock table connects Stores and Product in a many-to-many relationship implemented through Stock as a bridge entity. Each store carries many products, and each product can be stocked in multiple stores, with quantity levels stored in Stock. The Employee table links to Stores in a one-to-many relationship, showing that multiple employees work in one store. It also has a self-referencing relationship where an employee can manage other employees, modeling a managerial hierarchy within the same table. Finally, Orders connect back to Stores indirectly through Employees and Customers, ensuring that every transaction can be traced to both a customer and a physical location.
Overall, this model efficiently supports business operations such as tracking sales, managing inventory, and organizing staff responsibilities. The chosen relationship types ensure data consistency — for example, every product detail ties to exactly one product, while inventory and sales can scale across multiple stores and customers. This balance of one-to-one, one-to-many, and many-to-many structures provides both normalization and flexibility for future business growth.

<img width="892" height="733" alt="SQLProjectDataModelImage" src="https://github.com/user-attachments/assets/8337c60e-26e6-4089-8a54-1c85048dfe9e" />


## Data Dictionary
<img width="608" height="776" alt="dd1" src="https://github.com/user-attachments/assets/44a78b02-dc85-4cd9-a5a5-2ff7b1b14835" />
<img width="612" height="731" alt="dd2" src="https://github.com/user-attachments/assets/f79aa584-c186-4c56-b600-b04abf83066a" />
<img width="628" height="830" alt="dd3" src="https://github.com/user-attachments/assets/ed7b2800-34b3-4f24-83ff-f216a6520714" />
<img width="628" height="891" alt="dd4" src="https://github.com/user-attachments/assets/689e6454-5f9a-4133-959c-f9c21c5f653c" />
<img width="630" height="866" alt="dd5" src="https://github.com/user-attachments/assets/8307cacf-95c8-4d74-83d6-a7896a2e1e5f" />
<img width="634" height="207" alt="dd6" src="https://github.com/user-attachments/assets/2c48d451-4b3c-4898-8694-6ff3697848d3" />



## Ten Queries
<img width="3290" height="1647" alt="image" src="https://github.com/user-attachments/assets/86f5306e-e061-4e25-a957-fc2a450143f4" />

1. Query 1 finds the total number of employees working under each manager.
This query uses a self-join on the employee table to determine how many employees report to each manager.
By comparing manager_id in the employee records with employee_id in the manager records, it counts the total number of direct reports per manager. The GROUP BY clause groups results by manager, and COUNT() provides the number of employees under each.
   
<img width="2352" height="758" alt="Screenshot 2025-10-26 225717" src="https://github.com/user-attachments/assets/c06da333-516c-4c13-822f-8e8b1e7c4807" />

Managerial Justification:
A manager or HR leader would use this query to analyze organizational structure and span of control.
It helps identify which managers oversee larger or smaller teams, allowing leadership to evaluate workload distribution, managerial effectiveness, and opportunities to balance responsibilities across departments.

2. This query calculates the total sales revenue for each store, grouped by product category. It joins four tables — order_item, product, category, and stores — to connect each sold product to its category and store. The SUM(order_item.list_price) function adds up the total revenue generated from all sales within each store and category combination.

<img width="1883" height="1003" alt="Screenshot 2025-10-26 230129" src="https://github.com/user-attachments/assets/d5344049-c607-41c3-b081-03332f0c0f45" />

Managerial Justification:
From a managerial perspective, this query helps decision-makers evaluate store performance by product type. It identifies which categories generate the most revenue in each location, allowing managers to adjust inventory levels, marketing efforts, and shelf space allocation to maximize profitability and meet local customer demand.

3.  This query uses a correlated subquery to determine which customers have purchased items from more than three distinct product categories. The inner subquery counts the number of unique category_id values per customer by joining the orders, order_item, and product tables. The outer query filters for customers where that count is greater than three.

<img width="1216" height="996" alt="Screenshot 2025-10-26 230548" src="https://github.com/user-attachments/assets/4046a3e5-104c-4867-b14c-cd20baed0073" />

Managerial Justification:
 From a managerial perspective, this query highlights diverse or high-value customers who purchase across multiple product categories. These customers represent strong cross-selling opportunities, brand loyalty, and potential candidates for premium promotions or targeted marketing campaigns. Understanding which customers buy from various categories can help refine marketing strategies and loyalty programs.

4. Explanation Part 1

5. Explanation Part 1

6. Explnation Part 1

7. Explanation Part 1

8. Explanation Part 1

9. Explanation Part 1

10. Explanation Part 1 






## Database Information
[Insert Database Info Table here]
The Name of the Database is: cs_bck81809
