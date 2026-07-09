# 📊 Data Import & Transformation using Power BI

## 📌 Objective

The objective of this task is to import the E-commerce datasets into **Power BI** and prepare them for analysis using **Power Query Editor** by performing data cleaning, transformation, aggregation, and relationship creation.

---

## 📂 Datasets Used

| Dataset                | Description                                                                                        |
| ---------------------- | -------------------------------------------------------------------------------------------------- |
| **List of Orders.csv** | Contains order-level information such as Order ID, Order Date, Customer Name, State, and City.     |
| **Order Details.csv**  | Contains product-level information including Category, Sub-Category, Quantity, Amount, and Profit. |
| **Sales Target.csv**   | Contains monthly sales target information for comparison with actual sales.                        |

---
## 🔑 Key Transformations Performed

* ✅ **Applied the Keep Top Rows transformation** to retain the first **500** records.
* ✅ **Changed the data type** of the **Amount** and **Target** columns to **Fixed Decimal Number**.
* ✅ **Formatted text** using **Transform → Format → Capitalize Each Word (Proper Case)**.
* ✅ **Created custom columns** using **Add Column → Custom Column**.
* ✅ **Created the Profit Margin column** using the formula:

```powerquery
=[Profit] / [Amount]
```

* ✅ **Created the Location column** by combining the **City** and **State** columns.
* ✅ **Created a Conditional Column** to categorize profit status.
* ✅ **Merged queries** using **Home → Merge Queries → Merge Queries as New**.
* ✅ **Used a Left Outer Join** to combine the **List of Orders** and **Order Details** tables.
* ✅ **Sorted records** by **Order Date** in **Descending Order**.
* ✅ **Applied filters** to display records for the selected state.
* ✅ **Duplicated the Order Details table** for aggregation.
* ✅ **Grouped data** to calculate:

  * Count of **Order ID**
  * Average Profit by **Category**
  * Total Amount by **Sub-Category**
* ✅ **Duplicated the Sales Target table** and grouped data to calculate the **Total Target by Month**.
* ✅ **Created relationships** between tables in the Power BI data model.
# 🔹 Task 9: Create Relationships

## Relationship 1

| Property       | Value             |
| -------------- | ----------------- |
| Table          | List of Orders    |
| Column         | Order ID          |
| Related Table  | Order Details     |
| Related Column | Order ID          |
| Relationship   | One-to-Many (1:*) |

---

## Relationship 2

| Property       | Value             |
| -------------- | ----------------- |
| Table          | Order Details     |
| Column         | Category          |
| Related Table  | Sales Target      |
| Related Column | Category          |
| Relationship   | Many-to-One (*:1) |

---

# 📈 Relationship Summary

| Table 1        | Column   | Table 2       | Column   | Relationship      |
| -------------- | -------- | ------------- | -------- | ----------------- |
| List of Orders | Order ID | Order Details | Order ID | One-to-Many (1:*) |
| Order Details  | Category | Sales Target  | Category | Many-to-One (*:1) |

---

# 🛠 Tools Used

* Microsoft Power BI
* Power Query Editor
* CSV Files
* Data Modeling

---

# ✅ Transformations Performed

* Imported CSV datasets
* Kept Top 500 rows
* Changed data types
* Formatted text
* Created custom columns
* Added conditional columns
* Merged queries
* Sorted records
* Filtered data
* Grouped and aggregated data
* Created relationships between tables

---

# 🎯 Outcome

The datasets were successfully cleaned, transformed, and modeled using **Power Query Editor** in Power BI. The resulting data model is ready for creating interactive dashboards, reports, KPIs, and business insights.







-





