
# SQL Project 1 | Group 1
Members: Ben Kim, Jackson Avey, Christian Hertzig, Success Onichabor, Drew Vajda
[Insert Scenario here]





## Data Model
Explanation:
The Bike Store data model captures how products, customers, employees, and orders interact across multiple store locations. It is built around a set of well-defined relationships that mirror the real-world structure of a retail business. At the heart of the design is the Product table, which connects to several entities. Each product belongs to exactly one Brand and one Category, forming two one-to-many relationships from Product to Brand and Category. This means a single brand or category can be associated with many products, but each product can only have one brand and one category. The Product_Detail table is linked to Product through a one-to-one relationship because each product has a unique set of detailed attributes such as model year and list price that apply to that specific item only.
Sales transactions are modeled through the Orders and Order_Item tables. The Orders table connects to Customer in a one-to-many relationship since a single customer can place many orders, but each order belongs to only one customer. Each Order can also have multiple items, leading to a one-to-many relationship between Orders and Order_Item. On the other side, each Order_Item references a single Product, but a product can appear in many order items over time, forming another one-to-many relationship from Order_Item to Product. The Order_Item table serves as an associative entity, enabling a many-to-many conceptual link between Orders and Product while storing key transactional attributes like quantity, discount, and price at the item level.
Inventory and store management are supported by the Stores, Stock, and Employee tables. The Stock table connects Stores and Product in a many-to-many relationship implemented through Stock as a bridge entity. Each store carries many products, and each product can be stocked in multiple stores, with quantity levels stored in Stock. The Employee table links to Stores in a one-to-many relationship, showing that multiple employees work in one store. It also has a self-referencing relationship where an employee can manage other employees, modeling a managerial hierarchy within the same table. Finally, Orders connect back to Stores indirectly through Employees and Customers, ensuring that every transaction can be traced to both a customer and a physical location.
Overall, this model efficiently supports business operations such as tracking sales, managing inventory, and organizing staff responsibilities. The chosen relationship types ensure data consistency — for example, every product detail ties to exactly one product, while inventory and sales can scale across multiple stores and customers. This balance of one-to-one, one-to-many, and many-to-many structures provides both normalization and flexibility for future business growth.

<img width="892" height="733" alt="SQLProjectDataModelImage" src="https://github.com/user-attachments/assets/8337c60e-26e6-4089-8a54-1c85048dfe9e" />




## Data Dictionary
[Data.Dictionary.sqlproject1.pdf](https://github.com/user-attachments/files/23144820/Data.Dictionary.sqlproject1.pdf)


## Ten Queries
[Insert Queries and their Descriptions here]

## Database Information
[Insert Database Info Table here]
