# Retail-Cleanup
A detailed optimization of excel sheets to data models

# MB_B7| Enoch Faminu Project leader | Riya Jegajeevan Conceptual modeler | Justin Wu SQL Writer | Samandar Farkho Database designer and Data Wrangler

# Case Summary
Northline Outfitters is a small online retail company that sells student-friendly lifestyle and tech accessories. It purchases
merchandise from outside vendors and sells directly to consumers in the United States and Canada. Because it the company is small and still growing it houses most of its data in excel spreadsheets. Our Job is to transfer that into cleaerer and more efficient databases.

# Conceptual Model
<img width="431" height="380" alt="image" src="https://github.com/user-attachments/assets/02a8f0c4-68ef-43a2-bb59-6a2eb182d6ba" />

# Model Characteristics
The entities include Product, Orders, Order details, Costumers, Vendor, Shipment, Discount, Country and Employee. A key relationship is order details which is the many to many relationship of products to orders. This indicates details of the order including Unit price of the order and etc. Employee is its own table as manager references the employee numbers. Order has the most relationships, as most things run through it. It is the many side of employee, customer, shipment and order details. Product is the many side of country and confession. There is also a recursive relationship within products for mother products

# Data quality asssessment
The source file contains several notable data quality issues affecting consistency, completeness, validity, and structure. A major problem is inconsistent data formatting, particularly in date fields where multiple formats such as “10-11-2025,” “Oct 17 25,” and “June 11 2025” are used, preventing reliable interpretation and analysis. Currency-related fields are also inconsistent, with values like “USD 18.99” or “CAD 46.99” stored as text and line totals sometimes including symbols and sometimes not, which disrupts calculations. The tax and discount columns further complicate analysis by mixing percentages, decimals, whole numbers, and text labels like “promo5” or “student 10%,” making standardization difficult. Additionally, the size or weight field includes inconsistent units (inches vs. centimeters) and non-numeric values such as “one size,” limiting comparability. The dataset also suffers from missing values in key columns like tax, line total, size or weight, and return flags, which can lead to incomplete or inaccurate insights. Structural issues are present as well, with some columns combining multiple pieces of information (e.g., customer details in one field), violating normalization principles and reducing usability. Lastly, categorical fields such as payment methods show inconsistent capitalization (e.g., “VISA” vs. “visa”), leading to duplicate categories in analysis. Overall, these issues significantly reduce the dataset’s reliability and require thorough cleaning before meaningful analysis can be conducted.

# Data cleaning process
Sales Dump

Removed duplicate order ids

Made all values in sale_date to one consistent format

Split customer info into customer_F_Name, customer_L_Name, customer_type, and student_location

For customer_email, some customers are in the database, but for another order their email is not present. 

Changed all values in payment_method to a consistent format 

Changed quantity column to integers only

Changed discount column to integer only

Created a student column to identify students

Added a currency column to distinguish which type of currency (USD or CAD) Changed unit price to integers 

Separated size and weight, and made those columns integers only. Also, made all consistent unit (grams and centimeters) 

Product_Supplier_Master

Changed vendor_phone to one consistent format

Made currency column to differentiate which type of currency (USD or CAD)

Made the cost column all integers

Made list_price column all integers

Made separate columns for weight and size, and made those columns integers only. Also made all values consistent values (grams and centimeters)

# Queries
Which products generated the highest total sales revenue, by country?
<img width="618" height="651" alt="image" src="https://github.com/user-attachments/assets/1cf9f4fb-91dd-4712-b443-99376cdfb39e" />

Which employees handled the largest number of orders, and how do their results compare with other employees under the same manager?
<img width="780" height="790" alt="image" src="https://github.com/user-attachments/assets/00f2df8f-4fa2-4982-ab97-878fc36c7053" />

Which vendors supply products that appear in more than one category?
<img width="767" height="802" alt="image" src="https://github.com/user-attachments/assets/d216c300-7e1d-450a-ba37-aa83b67a5ff7" />

Which customers generate the highest lifetime value, and what is their average order size?
<img width="781" height="801" alt="image" src="https://github.com/user-attachments/assets/735639d7-6a62-463c-b2e1-2d133ed230f7" />

Which shipments are associated with the highest-value orders?
<img width="761" height="790" alt="image" src="https://github.com/user-attachments/assets/26d384e7-75f6-4657-b08a-2c51eec3682f" />

Which products have declining sales trends over time?
<img width="762" height="776" alt="image" src="https://github.com/user-attachments/assets/e995be31-fe4b-445e-aa30-14b801b67066" />




