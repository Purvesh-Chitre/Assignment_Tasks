# Assignment_Task_1

## Sales CRUD Operations Assignment

### Overview

This project demonstrates CRUD operations (Create, Read, Update, Delete) using SQLite and Python. Users can manage sales records dynamically via user input.


### Features

Create sales records
Retrieve and display sales data
Update existing sales records
Delete records
Exception handling for database operations


### Prerequisites

Ensure you have Python 3.x installed.

#### Install dependencies

Run the following command:
pip install pandas

#### Usage

Run the script with:
python scripts/sales_crud.py

#### Sample Operations

1 Insert a Record
Enter product name: Laptop  
Enter quantity: 2  
Enter price: 1200.50  
Enter sale date (YYYY-MM-DD): 2024-02-01  

- Record inserted successfully!

2 Read Records
   id   product   quantity   price    sale_date  
   1    Laptop    2         1200.50  2024-02-01  

3 Update a Record
Enter product name to update: Laptop  
Enter new price: 1100.00  
- Record updated successfully!

4 Delete a Record
Enter product name to delete: Laptop  
- Record deleted successfully!

### License
This project is open-source and free to use.
