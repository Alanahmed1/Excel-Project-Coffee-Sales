# Excel Coffee Sales DashBoard
![1_Sales_Dashboard](/Assets/DASHBOARDE.gif)

## Introduction

This Coffee Sales Data Dashboard was created to help businesses and analysts explore sales trends, customer behavior, and product performance within the coffee industry.

The data is sourced from a fictional coffee business and includes detailed information on:
- Orders
- Customer demographics
- Sales by country
- Product performance

This Excel file provides an interactive platform for analyzing metrics such as:
- Total sales
- Top customers
- Sales distribution across different regions

By utilizing this dashboard, businesses can make informed decisions based on data-driven insights. 

Additionally, this project serves as a practical example of leveraging Excel for data analysis, making it an excellent resource for learners interested in mastering data organization and visualization techniques.

### Dashboard File
My final dashboard is in [Coffee_Sales_Dashboard.xlsx](/coffee_Orders_Data.xlsx)

### Excel Skills Used:
The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🔍 Power Query**
- **💪 Power Pivot**

# 📊 Data Sales Dataset

### 🛒 Order :
***Order ID, Order Date, Customer ID, Product ID,and Quantity***

### 👤Customer:
***Customer ID, Customer Name, Email, Phone Number, Address, City, Country, Postcode, and loyalty card.***

### ☕ Product**

***Product ID, Coffee Type Name, Roast Type, Size, Unit Price, Price per 100g, and Profit***

# Dashboard Build

### 🔍 Data Cleaning with Power Query (ETL)


1. **Table Creation**  
   - Started by creating tables from the raw data: `Order`, `Customer`, and `Product`.

2. **Load to Power Query**  
   - Loaded all the raw data tables into the Power Query editor.

3. **Transformations Applied**  
   - Changed column data types to ensure consistency (e.g., dates, numbers, text).  
   - Removed unnecessary columns to streamline the data.  
   - Cleaned text values to eliminate specific unwanted words.  
   - Trimmed excess whitespace for better formatting.  

4. **Merging Tables**  
   - Merged the `Order` table with the `Product` table to bring in the `Unit Price` column into the `Order` table.

5. **Adding Computed Columns**  
   - Created a new `Sales` column in the `Order` table by multiplying `Unit Price` and `Quantity`.

![1_Sales_Dashboard-PowerQuery](/Assets/Order-Merge-Query.png)
With Power Query, I was able to efficiently clean, transform, and enrich the raw data, preparing it for analysis.

### 🧮 Data Analysis with PivotTables & DAX

#### 🔗 Establishing Relationships Between Tables
After cleaning the data, I used **PivotTables** and **DAX** to analyze and visualize the data. The first step was to use **Power Pivot** in order to create relationships between the tables:

### 🔗 Relationships:
1. **Order → Customer Relationship**
   - Based on `Customer ID`.
   - This relationship allowed the analysis of customer purchase patterns and loyalty card usage.

2. **Order → Product Relationship**
   - Based on `Product ID`.
   - This relationship enabled detailed sales and profit analysis by product attributes (e.g., Coffee Type, Roast Type).    

![1_Sales_Dashboard-relations](/Assets/Relations.gif)

### Advanced Analysis with Power Pivot and DAX

After preparing the data and creating relationships in **Power Pivot**, I utilized **DAX** and **PivotTables** to perform advanced analyses and build dynamic visualizations. Here's how I achieved it:

### Total Sales Over Time
I analyzed sales trends over time, categorized by coffee types, and presented the results in a **Line Chart**:
- **Columns**: `Coffee Type Name` (from the Product Table).
- **Rows**: `Order Date` displayed by **Year** and **Month** (from the Order Table).
- **Values**: `Sales` calculated using DAX:
  ```DAX
  Total Sales = SUM(Order[Sales])
 The line chart highlighted seasonal patterns and performance trends for different coffee types.

 ### Sales by Country
 I visualized sales performance across countries using a **Bar Chart**:
 - **Columns**: `Country` (from the Customer Table).
- **Values**: `Sales` calculated 

The bar chart displayed total sales for each country, making it easy to identify high-performing regions.

### Top 5 Customers
I showcased the top contributors to sales with a **Bar Chart** and a **complementary table**:

**Rows**: Customer Name (from the Customer Table).  
**Values**: Sum of Sales from the Order Table.  
**DAX Measure**: Ranked customers based on their total sales to identify the top 5: 
  ```DAX
  Rank = RANKX(ALL(Customer), [Total Sales], , DESC)
```
![1_Sales_Dashboard-Top5Customers](/Assets/Top_5_Customers.png)
***The PivotTable was filtered to display only the Top 5 Customers, and the results were presented in a bar chart alongside a table, providing both graphical and tabular insights***.

## Slicers and Timeline Integration ☕️

### Slicers
These interactive filters enhance data exploration and analysis. 

* **Roast Type roasted_bean:**
  * Filter by coffee roast type (Light, Medium, Dark)
  * Dynamically updates graphs and tables for easy comparison

* **Size 📏:**
  * Filter by coffee size (0.2kg , 0.5kg, 1 kg, 2.5kg)
  * Gain insights into customer preferences

* **Loyalty Card 💳:**
  * Filter by customer loyalty status (Yes/No)
  * Analyze the impact of loyalty programs on sales and behavior

**Timeline 📅**  
This time-based filter allows for granular data exploration.

* **Filter by Time Period**
  * Select specific years, months, or custom ranges
  * Connected to the `Order Date` field for precise temporal filtering
  * Dynamically updates PivotTables and charts for trend analysis         
# Key Insights from Data Analysis 📊

### **1. Customer Loyalty Drives Significant Sales 💳**
Customers with loyalty cards contribute a notable portion of sales. 
* **Insight:** Implement or expand loyalty programs to incentivize repeat purchases and build long-term customer relationships.

### **2. Top Customers Account for a Substantial Share of Revenue 👑**
A small percentage of customers generate a disproportionately high share of total sales. 
* **Insight:** Focus on retaining top customers by offering personalized promotions, exclusive discounts, or early access to new products.

### **3. Regional Sales Trends Highlight Key Markets 🌍**
Certain regions (e.g., US, UK) are leading in sales. 
* **Insight:** Expand marketing efforts, introduce region-specific products, or scale operations in these high-performing markets.

### **4. Coffee Type and Roast Preferences Vary by Time and Region 📅**
Seasonal or monthly trends in preferences for different coffee types and roasts are evident. 
* **Insight:** Align seasonal marketing campaigns with consumer preferences to boost sales.

### **5. Product Size Impacts Customer Choices 📏**
Varying preferences for coffee sizes are observed.
* **Insight:** Adjust inventory or bundling promotions to match popular sizes in key regions, optimizing sales and minimizing stock wastage.

**Summary of Insights**  
By leveraging data preparation, visualization tools, and interactive dashboards, actionable insights into customer behavior, product performance, and market trends have been uncovered. These findings can guide strategic decisions to optimize sales, improve customer retention, and tailor product offerings.

# Conclusion

This Excel-based project delves into the world of coffee sales, leveraging data visualization and analysis techniques to extract valuable insights. By harnessing the power of Power Pivot, DAX, and interactive dashboards, we've explored key trends, customer preferences, and regional sales patterns.

This project serves as a practical demonstration of how Excel can be used to uncover actionable insights from complex datasets. It highlights the importance of data-driven decision-making in the coffee industry and provides a foundation for further exploration and optimization.