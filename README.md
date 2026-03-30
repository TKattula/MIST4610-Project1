# MIST4610-Project1
## Team Memebers & Repos
Tanvi Kattula @Tkattula\
Maddie Wrigley\
Jessica Downen @JessicaDownen \
Darren Zhang @darrenzhang11

## Problem Description

*The goal of Project 1 is to model, build and query a relational database.* We created our database to help support a department store, like Macy's or JCPenny, core department store operations including employees, products, departments, sales and customers. We made it scaleable so that smaller store would be able to populate and use the database meanfully in the businesses.

The 'Store' includes the physical location of the store, and connects many tables including StoreInventory, Employees, SalesOrder, Address and Retruns. These tables work in conjunction with eachother to create a functional database that allows the user to make valid and insightful queries. Our database allows the user to manage inventory, customer orders, returns and locations amoung other things which would solve a variey of issues a client using our database would like to solve. At its core, our dataabase is meant to solve issues that arise in retail settings such as: inventory management, customer order management, as well as maintaining accurate records of important data. 


## Data Model

Explanation:

Our data model represents the inner working of a department store. It allows the users to manage multiple areas like products, stores, orders, inventory, etc. We have connected each table to help create a natural flow of information to the user and allowing the database to have a greater sense of functionality and value to the user. 

The customer table allows us to record customer information that would be useful to identify the customer. Each customer will have their own specific ID that allows the user to identify specific cusotmer information. The information that goes into this table could be collected when the cusotmer creates an account. Customers can have loyalty accounts to the specific store as well. Loyalty accounts record information on their own loyalty number (similar to a libray number or a Costco Card) and how many points the customer has collected. Each customer can only have one loyalty account and each loyalty account can only be linked to one customer.

When customer a opens a account they will put in their address information as well which is stored in the address table, this table stores information on their street name and has a one to many relationship with the postal code table which stores information on the specific city and state. The postal code is always unique and is never repeated so it also functions as the primary key for the postal code table. The address table take the postal code from the postal code table and its own data combines them to create each each address in address the postal code can be repeated as it functions as foregin key. The address table and customer table come together to form a many to many table to record each customers address. Each address in that table can be linked to a specific customer and can be recorded as either a shippinf or billing addess for any customer with differing addesses. 

When customers actually place their order all of that information goes into the sales order table. The sales order table has information on which employee helped place the order, which customer the order is for, and which store placed the order and the date and type for order placed. Each order is unique and can not have a matching order number with any other order in the table. The salesorder table braches off into the customer table which will help in indentifying the cusotmers information, the payment table which simply records the payment amount, how its paid (method - cash, card, check) and which order its paying off. Another branch is the return table which is a another simple table that has the customer, order, and store in the same place if the customer wanted to have a refund on a order it would be able to link all of that information together. For sales order, its important to know which employee had assited in placing the order and employee is a one to many relationship with the employee table. Store is another branch of the sales order table which lets us see which store the order was placed at.

The store acts like a store location list essentially. It provides information on the stores name, address, phone number, and manager of the store. The address for each store is also stored in the address table so it forms a one to one relationship with that table since a store can only have one address and one address can only have one store. Store only have one manager so the employee table is a one to many and a the relationship between the store and manager is a special relationship as one employee is the manager of the store. 

The product table holds information on each type of item the store carries like the SKU, name, brand, size, description, color, price, and quantity. It is a very important table since it holds information on the product, price and quantity. This table branches off into the store inventory table which also gets information from the store table which forms a many to many relationship. The store inventory table has information about which store has how much of each product (quantity) and also the amount of an item they currently have available to sell. The department table also branches into the product table. The department table is helpful since it holds information on the which department the product belongs in like gender, age, season and type of product, and it branches into the product table so that the user can see which product belongs to which department. 

And lastly are the orderline and returnline tables which are very important because they bridge two important table. For instance the OrderLine table bridges together the sales order and products table into a many to many relationship. These tables are important since they aviod redundancy in the example of orderline a order can have many products and a product can have many orders. The returnline table functions the same way as the orderline table expect it bridges together the return and product table. 

## Data Dictionary

<img width="708" height="401" alt="Screenshot 2026-03-29 at 10 32 21 PM" src="https://github.com/user-attachments/assets/6f6fa999-8645-46aa-8216-dc92733d8d4f" />

<img width="695" height="341" alt="Screenshot 2026-03-29 at 10 32 29 PM" src="https://github.com/user-attachments/assets/7ca1f5c4-4b3a-45c0-a9c5-b012be91d396" />

<img width="692" height="244" alt="Screenshot 2026-03-29 at 10 36 23 PM" src="https://github.com/user-attachments/assets/47f339b3-7f5b-499f-9dec-139cbab81cac" />

<img width="689" height="586" alt="Screenshot 2026-03-29 at 10 29 58 PM" src="https://github.com/user-attachments/assets/1d652deb-d527-4d13-a99c-f8f5df850067" />

<img width="678" height="523" alt="Screenshot 2026-03-29 at 10 30 25 PM" src="https://github.com/user-attachments/assets/27da7dac-ff21-408b-b09c-31a656e44731" />

<img width="667" height="252" alt="Screenshot 2026-03-29 at 10 30 34 PM" src="https://github.com/user-attachments/assets/d2f0e78d-f7a6-45a3-ae4f-0859f65cce5f" />

<img width="677" height="453" alt="Screenshot 2026-03-29 at 10 30 55 PM" src="https://github.com/user-attachments/assets/2bba8fab-ccd2-41c7-abf3-6241e3303e92" />

<img width="655" height="271" alt="Screenshot 2026-03-29 at 10 31 02 PM" src="https://github.com/user-attachments/assets/a8840882-cfdb-4be6-ac1f-cbf5f2f95302" />

<img width="696" height="535" alt="Screenshot 2026-03-29 at 10 31 21 PM" src="https://github.com/user-attachments/assets/fb7b2b32-37f9-4b35-a90f-be3b8110a084" />

<img width="674" height="408" alt="Screenshot 2026-03-29 at 10 31 35 PM" src="https://github.com/user-attachments/assets/80ff3f60-8dac-4197-bbd8-6b56e3150733" />

<img width="646" height="493" alt="Screenshot 2026-03-29 at 10 29 50 PM" src="https://github.com/user-attachments/assets/db2963d5-e0cc-471b-a145-46e765bb8c58" />

<img width="686" height="486" alt="Screenshot 2026-03-29 at 10 29 43 PM" src="https://github.com/user-attachments/assets/fa2aae07-b5e2-462b-80f7-3e666f1637dc" />

<img width="609" height="523" alt="Screenshot 2026-03-29 at 10 29 35 PM" src="https://github.com/user-attachments/assets/6db07792-3114-4e22-b87e-1e3b817cffd3" />

<img width="670" height="332" alt="Screenshot 2026-03-29 at 10 28 11 PM" src="https://github.com/user-attachments/assets/3d4b8371-0631-4ff9-b116-fad20d604681" />

## Queries

## ChatGPT Conversations

## Database Information
