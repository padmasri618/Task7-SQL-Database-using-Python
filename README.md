# Sales Summary Report using SQL in Python

## Objective

The goal of this project is to demonstrate how to:
- Create a simple SQLite database using Python
- Insert sales data into a table
- Run SQL queries inside Python to analyze total sales and revenue
- Visualize the results using `matplotlib` bar charts

---

## Dataset Explanation

This project uses a small, manually inserted dataset in SQLite with the following schema:

## Column        Type       Description                     
*  id           INTEGER    Auto-increment primary key      
*  product      TEXT       Name of the product             
*  quantity     INTEGER    Quantity sold                   
*  price        REAL       Price per unit of the product   

## Sample Data Used

 ## Product Quantity   Price 

* Pen         10         1.5   
* Notebook    5          3.0   
* Pencil      20         0.5
* Eraser      15         0.75  
* Pen         7          1.5   
* Notebook    3          3.0   
* Pencil      10         0.5   

---

##  Code Usage

## File: `create_sales_data.py`

- Creates a new SQLite database file `sales_data.db`.
- Defines a `sales` table.
- Inserts 7 sample records.

##  File: `sales_summary_analysis.py`

- Connects to `sales_data.db`
- Executes SQL to calculate:
  - Total quantity sold per product
  - Total revenue (quantity × price) per product
- Loads the results into a Pandas DataFrame
- Prints a summary table
- Visualizes revenue per product in a bar chart
## SQL Query Used

``sql
SELECT 
    product, 
    SUM(quantity) AS total_qty, 
    SUM(quantity * price) AS revenue 
FROM sales 
GROUP BY product

### Insights

- Pen generated the highest total revenue due to being sold in high quantity with a decent price.

- Notebook contributed significantly with fewer units but higher unit price.

- Pencil had high quantity sales but low total revenue due to low price.

- The Eraser has a mid-range revenue due to moderate quantity and price.
---
 ## Anomalies
- No timestamps (e.g., sale_date) in the dataset — cannot analyze sales trends over time.

- Duplicate product names exist (e.g., multiple "Pen" entries), which are expected but grouped properly via SQL.
---


##  Visualization
### Revenue by Product
![Monthly Revenue Bar Chart] ![Uploading Monthly Revenue Bar Chart.png…]()

---
## Task Outcomes
     Step	                            Outcome
* SQLite DB Creation	   Successful creation and data insertion
* SQL Query Execution 	 Accurate grouping and aggregation of data
* Summary Table	         Clean and readable using pandas
* Visualization	         Informative revenue bar chart per product

---

## Conclusion
- This project successfully demonstrates how SQL can be integrated into Python workflows for basic sales reporting.

- It combines SQL querying power with Python’s visualization (matplotlib) and data handling (pandas).

- Suitable for small-scale analysis and teaching the fundamentals of embedded database reporting in Python.

