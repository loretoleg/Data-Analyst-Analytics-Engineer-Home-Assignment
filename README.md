# Troubleshooting and Data Management Documentation

This README contains a series of questions and answers related to troubleshooting data issues, creating reports, and managing data pipelines. Below, you'll find the details of each question along with the corresponding answer. This will serve as a guide to understand the troubleshooting process and address common data-related challenges.

---

## Task 1: Data Modeling & ETL

### 1. Database Setup

Imagine you’re building a dashboard to track orders, customers, and inventory for a food
delivery business.
Create a simplified schema that includes the following tables:
- `Customers`: customer_id, name, registration_date, and region.
- `Orders`: order_id, customer_id, order_date, total_amount.
- `Items`: item_id, item_name, item_price, and inventory_stock.
- `Order_Items`: order_id, item_id, quantity.

### Deliverable
- Provide SQL code for creating these tables.
- Write a short paragraph explaining your rationale for the structure

**Answer:**

The database design is straightforward and simple, with normalization applied to eliminate data redundancy. Primary keys have been assigned to each table to uniquely identify records and ensure data integrity. This design helps maintain data consistency and reduces redundancy across the database. One potential improvement would be to assign a surrogate primary key to the order_items table. By doing so, we could eliminate the need for a composite key (which currently uses order_id and item_id), improving query performance and making the database easier to maintain over time.
To make future troubleshooting easier, I’d create a checklist of potential issues. This would help me quickly diagnose similar problems down the road and ensure that troubleshooting steps are well-documented for consistency.

I started by creating a postgresql database using AWS RDS for hosting.

The SQL code for table creation is shown below:

![SQL Image](./images/sql.png)

![SQL Image](./images/table_creation.png)

Then, I wanted a visualization of the database, so I logged into pgAdmin 4 to obtain the following image: 

![SQL Image](./images/schema_viz.png)

Finally, I loaded data into it using the faker python library:

![SQL Image](./images/faker.png)


---
