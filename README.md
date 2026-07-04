Data Import & Transformation
Objective
The objective of this task is to import the E-commerce datasets into Power BI and prepare them for analysis using Power Query Editor.


Datasets Used
• List of Orders.csv – Contains order-level information such as Order ID, Order Date, Customer Name, State, and City.
• Order Details.csv – Contains product-level information including Category, Sub-Category, Quantity, Sales, and Profit.
• Sales Target.csv – Contains monthly sales target information for comparison with actual sales.


1.Restrict the List of Orders Table to the First 500 Rows
• Selected the List of Orders table.
• Navigated to Home → Keep Rows → Keep Top Rows.
• Applied the transformation to keep only the first 500 records.


2.Change the Amount and Target Columns to Fixed Decimal Number
• Selected the Target column in the Sales Target table.
• Changed its data type to Fixed Decimal Number Confirmed that both columns displayed numeric values with fixed decimal precision.


3.Text Formatting
• Selected the Customer Name column in the List of Orders table.
• Navigated to Transform → Format → Capitalize Each Word (Proper Case)



4.Column Creation:
• Selected the Order Details table.
• Navigated to Add Column → Custom Column.
• Created a new column named Profit Margin.
• Used the following formula
         =[Profit] / [Amount]
Location – Combines the City and State columns into a single field in the format City, State.



5. Conditional Column:
• Selected the Order Details table.
• Navigated to Add Column → Conditional Column.
• Created a new column named Profit Status


6.Merging Data (Joins)
• Navigated to Home → Merge Queries → Merge Queries as New.
• Selected Order Details as the second table.
• Chose Order ID as the matching column in both tables.
• Selected the Left Outer (All from first, matching from second) join type.
• Clicked OK to create the merged query.


7. Sort Records by Order Date
• Selected the Orders Data table.
• Clicked the dropdown arrow on the Order Date column.
• Chose Sort Descending to display the most recent orders first.


7.1 Filter Records by State
• Clicked the filter dropdown on the State column.
• Selected Tamil Nadu from the list of available states.
• Applied the filter to display only orders from Tamil Nadu.


8. Duplicate the Order Details Table
• Right-clicked the Order Details table and selected Duplicate.
• Used Transform → Group By to perform the required aggregations.
 Count of Order ID
• Grouped by Order ID.
• Applied the Count Rows each order.


Average Profit by Category
• Grouped by Category.
• Created a new column named Average Profit.
• Selected Average as the aggregation operation on the Profit column.



Total Amount by Sub-Category
• Grouped by Sub-Category.
• Created a new column named Total Amount.
• Selected Sum as the aggregation operation on the Amount column.



Duplicate the Sales Target Table
• Right-clicked the Sales Target table and selected Duplicate.
• Used Transform → Group By to summarize the data.
Aggregate Total Target by Month
• Grouped by the Month of Order Date.
• Created a new column named Total Target.
• Selected Sum as the aggregation operation on the Target column.



9.Create Relationship Between List of Orders and Order Details
• Opened the Model View in Power BI.
• Selected Manage Relationships from the Home tab.
• Created a new relationship using:
• Table: List of Orders
• Column: Order ID
• Related Table: Order Details
• Related Column: Order ID
• Set the relationship as One-to-Many (1:*)




10.Create Relationship Between Order Details and Sales Target
• Opened Manage Relationships.
• Created a new relationship using:
• Table: Order Details
• Column: Category
• Related Table: Sales Target
• Related Column: Category
• Configured the relationship as Many-to-One (*:1) (or One-to-Many (1:*)




Relationship Summary
Table 1	Column	Table 2	Column	Relationship
List of Orders	Order ID	Order Details	Order ID	One-to-Many (1:*)
Order Details	Category	Sales Target	Category	Many-to-One (:1) or One-to-Many (1:), based on data





