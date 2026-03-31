# Team 8 MIST4610-Project1

## Team Name:
21479 Group 8
## Team Memebers & Repos
Tanvi Kattula [@Tkattula](https://github.com/TKattula) \
Maddie Wrigley [@Maddiekw1](https://github.com/Maddiekw1) \
Jessica Downen [@JessicaDownen](https://github.com/JessicaDownen) \
Darren Zhang [@darrenzhang11](https://github.com/darrenzhang11)

## Problem Description

*The goal of Project 1 is to model, build and query a relational database.* We created our database to help support a department store, like Macy's or JCPenny, core department store operations including employees, products, departments, sales and customers. We made it scaleable so that smaller store would be able to populate and use the database meanfully in the businesses.

The 'Store' includes the physical location of the store, and connects many tables including StoreInventory, Employees, SalesOrder, Address and Retruns. These tables work in conjunction with eachother to create a functional database that allows the user to make valid and insightful queries. Our database allows the user to manage inventory, customer orders, returns and locations amoung other things which would solve a variey of issues a client using our database would like to solve. At its core, our dataabase is meant to solve issues that arise in retail settings such as: inventory management, customer order management, as well as maintaining accurate records of important data. 

<img width="629" height="600" alt="Screenshot 2026-03-29 at 10 45 36 PM" src="https://github.com/user-attachments/assets/c80a75f0-5d73-4569-900b-a80d7f486e2b" />

## Data Model 

Explanation:

Our data model represents the inner working of a department store. It allows the users to manage multiple areas like products, stores, orders, inventory, etc. We have connected each table to help create a natural flow of information to the user and allowing the database to have a greater sense of functionality and value to the user. 

The Customer table allows us to record customer information that would be useful to identify the customer. Each customer will have their own specific ID that allows the user to identify specific customer information. The information that goes into the Customer table could be collected when the customer creates an account. Customers can have loyalty accounts to the specific store as well. The Loyalty Account table records information on their own loyalty number (like a library number or a Costco card) and how many points the customer has collected. Each customer can only have one loyalty account, and each loyalty account can only be linked to one customer.

When customer a opens an account, they will put in their address information as well which is stored in the Address table, this table stores information on their street name and has a one-to-many relationship with the postal code table which stores information on the specific city and state. The postal code is always unique and is never repeated so it also functions as the primary key for the Postal Code table. The Address table takes the postal code from the Postal Code table, and its own data combines them to create each address, in the Address table the postal code can be repeated as it functions as foreign key. The address table and customer table come together to form a many to many tables to record each customer’s address. Each address in that table can be linked to a specific customer and can be recorded as either a shipping or billing address for any customer with differing addresses. 

When customers place their order all that information goes into the SalesOrder table. The SalesOrder table has information on which employee helped place the order, which customer the order is for, and which store placed the order and the date and type for order placed. Each order is unique and cannot have a matching order number with any other order in the table. The sales order table Braches off into the Customer table which will help in identifying the customers information, the payment table which simply records the payment amount, how its paid (method - cash, card, check) and which order it paying off. Another branch is the Return table which is another simple table that has the customer, order, and store in the same place if the customer wanted to have a refund on an order it would be able to link all that information together. For SalesOrder, it’s important to know which employee had assisted in placing the order and employee is a one-to-many relationship with the SalesOrder table. Store is another branch of the SalesOrder table which lets us see which store the order was placed at.

The Store table acts like a store location list essentially. It provides information on the stores name, address, phone number, and manager of the store. The address for each store is also stored in the Address table so it forms a one-to-one relationship with that table since a store can only have one address, and one address can only have one store. Store only have one manager, so the Employee table is a one to many and the relationship between the store and manager is a special relationship as one employee is the manager of the store. 

The Product table holds information on each type of item the store carries like the SKU, name, brand, size, description, color, price, and quantity. It is a very important table since it holds information on the product, price and quantity. This table branches off into the StoreInventory table which also gets information from the Store table which forms a many to many relationships. The StoreInventory table has information about which store has how much of each product (quantity) and the amount of an item they currently have available to sell. The Department table also branches into the Product table. The Department table is helpful since it holds information on the which department the product belongs in like gender, age, season and type of product, and it branches into the Product table so that the user can see which product belongs to which department. 

And lastly are the OrderLine and ReturnLine tables which are very important because they bridge two important table. For instance, the OrderLine table bridges together the SalesOrder and Product table into a many to many relationships. These tables are important since they avoid redundancy in the example of OrderLine an order can have many products and a product can have many orders. The ReturnLine table functions the same way as the OrderLine table expect it bridges together the Return and Product table. 

## Data Dictionary

### SalesOrder

<img width="693" height="553" alt="Screenshot 2026-03-30 at 9 26 42 AM" src="https://github.com/user-attachments/assets/6aae41ef-115c-49d7-9a76-953f7f4bb96c" />

### Store

<img width="708" height="401" alt="Screenshot 2026-03-29 at 10 32 21 PM" src="https://github.com/user-attachments/assets/6f6fa999-8645-46aa-8216-dc92733d8d4f" />

### StoreInventory

<img width="695" height="341" alt="Screenshot 2026-03-29 at 10 32 29 PM" src="https://github.com/user-attachments/assets/7ca1f5c4-4b3a-45c0-a9c5-b012be91d396" />

### ReturnLine

<img width="692" height="244" alt="Screenshot 2026-03-29 at 10 36 23 PM" src="https://github.com/user-attachments/assets/47f339b3-7f5b-499f-9dec-139cbab81cac" />

### Employee

<img width="689" height="586" alt="Screenshot 2026-03-29 at 10 29 58 PM" src="https://github.com/user-attachments/assets/1d652deb-d527-4d13-a99c-f8f5df850067" />

### Loyalty Account

<img width="678" height="523" alt="Screenshot 2026-03-29 at 10 30 25 PM" src="https://github.com/user-attachments/assets/27da7dac-ff21-408b-b09c-31a656e44731" />

### OrderLine

<img width="667" height="252" alt="Screenshot 2026-03-29 at 10 30 34 PM" src="https://github.com/user-attachments/assets/d2f0e78d-f7a6-45a3-ae4f-0859f65cce5f" />

### Payment

<img width="677" height="453" alt="Screenshot 2026-03-29 at 10 30 55 PM" src="https://github.com/user-attachments/assets/2bba8fab-ccd2-41c7-abf3-6241e3303e92" />

### Postal Code

<img width="655" height="271" alt="Screenshot 2026-03-29 at 10 31 02 PM" src="https://github.com/user-attachments/assets/a8840882-cfdb-4be6-ac1f-cbf5f2f95302" />

### Product

<img width="696" height="535" alt="Screenshot 2026-03-29 at 10 31 21 PM" src="https://github.com/user-attachments/assets/fb7b2b32-37f9-4b35-a90f-be3b8110a084" />

### Return

<img width="674" height="408" alt="Screenshot 2026-03-29 at 10 31 35 PM" src="https://github.com/user-attachments/assets/80ff3f60-8dac-4197-bbd8-6b56e3150733" />

### Department

<img width="646" height="493" alt="Screenshot 2026-03-29 at 10 29 50 PM" src="https://github.com/user-attachments/assets/db2963d5-e0cc-471b-a145-46e765bb8c58" />

### CustomerAddress

<img width="686" height="486" alt="Screenshot 2026-03-29 at 10 29 43 PM" src="https://github.com/user-attachments/assets/fa2aae07-b5e2-462b-80f7-3e666f1637dc" />

### Customer

<img width="609" height="523" alt="Screenshot 2026-03-29 at 10 29 35 PM" src="https://github.com/user-attachments/assets/6db07792-3114-4e22-b87e-1e3b817cffd3" />

### Address

<img width="670" height="332" alt="Screenshot 2026-03-29 at 10 28 11 PM" src="https://github.com/user-attachments/assets/3d4b8371-0631-4ff9-b116-fad20d604681" />

## Queries

## Database Information
