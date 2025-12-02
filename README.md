
---

# **📊 SQL Exploratory Data Analysis (EDA) Project**  
*A comprehensive collection of SQL scripts for data exploration, analytics, and reporting.*  

![SQL EDA](https://www.sqlshack.com/wp-content/uploads/2020/08/sql_data_analysis.jpg)  

## 🚀 **Introduction**  
This repository contains **SQL queries** designed to help **data analysts, BI professionals, and data scientists** efficiently explore databases, generate insights, and build meaningful reports. Whether you're working with **large-scale transactional databases, data warehouses, or analytical datasets**, these scripts will serve as a **powerful toolkit** to accelerate your **data analysis** workflow.  

## 🎯 **Project Goals**  
- ✅ Provide a structured approach to **SQL-based EDA**.  
- ✅ Enable **quick database exploration** with essential queries.  
- ✅ Analyze **key measures and metrics** using SQL functions.  
- ✅ Perform **time-based trend analysis** and **cumulative analytics**.  
- ✅ Segment data into meaningful categories for better insights.  
- ✅ Optimize query performance using **indexing and best practices**.  

## 📂 **Repository Structure**  
This project is divided into multiple **SQL scripts**, each focusing on different aspects of **data analysis**.  

### **1️⃣ Database Exploration Queries**  
- 🔍 Get **table structures, columns, and data types**.  
- 🔍 Count **total records** in each table.  
- 🔍 Find **missing or null values** across datasets.  

### **2️⃣ Key Performance Metrics & Aggregations**  
- 📊 Compute **sum, average, min, max, and median** values.  
- 📊 Identify **top-selling products, high-value customers, and trends**.  
- 📊 Analyze **customer lifetime value (CLV) and churn rates**.  

### **3️⃣ Time-Based Trend Analysis**  
- 📈 Compare **sales growth month-over-month**.  
- 📈 Perform **year-over-year comparisons**.  
- 📈 Analyze **seasonality trends and peak periods**.  

### **4️⃣ Cumulative & Rolling Aggregates**  
- 🔄 Implement **running totals, moving averages, and percent changes**.  
- 🔄 Use **window functions** for advanced analysis.  
- 🔄 Forecast trends using **historical cumulative patterns**.  

### **5️⃣ Customer Segmentation & Behavioral Analytics**  
- 👤 Classify customers into **tiers (VIP, Regular, New)** based on spending.  
- 👤 Segment users based on **purchase frequency & recency**.  
- 👤 Identify **inactive users** for targeted engagement campaigns.  

### **6️⃣ Advanced SQL Techniques**  
- 🛠️ Use **Common Table Expressions (CTEs)** for better query organization.  
- 🛠️ Implement **JOINs (INNER, LEFT, RIGHT, FULL)** for combining datasets.  
- 🛠️ Optimize **query performance with indexing** and efficient filtering.  

---

## 📊 SQL Data Analytics Dashboard

This project features a **Tableau dashboard** analyzing SQL-based data. The dashboard provides insights into:

- **Key Metrics & Trends** 📈  
- **Geographical Analysis** 🌍  
- **User Behavior & Patterns** 👥  
- **Performance Comparisons** ⚖️  

### 🔍 **Dashboard Preview**
![Dashboard Preview](https://raw.githubusercontent.com/your-username/your-repository/main/image.png)

🔗 **Explore the Live Dashboard:**  
[Click here to view on Tableau Public](https://public.tableau.com/views/Book2_17423208511630/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## 🔥 **Sample SQL Queries**  
Here are some **sample queries** demonstrating different SQL techniques used in this project:  

### **🔹 Example 1: Find Top 10 Best-Selling Products**  
```sql
SELECT 
    product_id, 
    product_name, 
    SUM(sales_amount) AS total_sales
FROM gold_fact_sales
GROUP BY product_id, product_name
ORDER BY total_sales DESC
LIMIT 10;
```  

### **🔹 Example 2: Customer Segmentation Based on Spending**  
```sql
WITH customer_spending AS (
    SELECT 
        customer_id, 
        SUM(sales_amount) AS total_spent
    FROM gold_fact_sales
    GROUP BY customer_id
)
SELECT 
    customer_id,
    CASE 
        WHEN total_spent >= 5000 THEN 'VIP'
        WHEN total_spent BETWEEN 1000 AND 4999 THEN 'Regular'
        ELSE 'New'
    END AS customer_segment
FROM customer_spending;
```  

### **🔹 Example 3: Month-over-Month Sales Growth**  
```sql
WITH monthly_sales AS (
    SELECT 
        DATE_FORMAT(order_date, '%Y-%m') AS month, 
        SUM(sales_amount) AS total_sales
    FROM gold_fact_sales
    GROUP BY month
)
SELECT 
    month,
    total_sales,
    LAG(total_sales) OVER (ORDER BY month) AS prev_month_sales,
    (total_sales - LAG(total_sales) OVER (ORDER BY month)) / 
        LAG(total_sales) OVER (ORDER BY month) * 100 AS sales_growth_pct
FROM monthly_sales;
```  

---

## ⚙️ **Setup & Usage**  

### **1️⃣ Prerequisites**  
To run the SQL scripts, ensure you have:  
✅ A database management system like **MySQL, PostgreSQL, or SQL Server**.  
✅ Access to a dataset with **sales, customer, and product information**.  
✅ A SQL query editor like **MySQL Workbench, pgAdmin, or SSMS**.  

### **2️⃣ Running SQL Scripts**  
1. Clone this repository:  
   ```sh
   git clone https://github.com/udayvimal/sql-exploratory-data-analysis-project.git
   cd sql-exploratory-data-analysis-project
   ```  
2. Open your **SQL editor** and connect to the database.  
3. Execute the required SQL scripts from the repository.  

---

## 🎯 **Key Benefits**  
- 📌 **Reusable SQL templates** for quick EDA.  
- 📌 **Optimized queries** for better performance.  
- 📌 **Advanced techniques** like CTEs and window functions.  
- 📌 **Well-documented scripts** with clear explanations.  

---

## 👨‍💻 **About Me**  
Hi there! I’m **Uday Vimal**, a passionate **data engineer & AI enthusiast** with a strong background in **SQL, data analytics, and ETL pipelines**.  

🚀 My work revolves around **FastAPI, PostgreSQL, Apache Airflow, and Data Science**, where I build **AI-powered solutions** for real-world data problems.  

I’m constantly learning and sharing knowledge, working on **end-to-end data engineering and AI projects** to push the boundaries of innovation.  

---

## ⭐ **Support & Contributions**  
💡 If you find this project helpful, please consider **starring the repository** ⭐ and sharing it with fellow data enthusiasts!  

🛠️ **Contributions are welcome!** Feel free to submit a **pull request** with additional SQL scripts or improvements.  

🚀 **Let’s explore data together!** Happy coding! 🎉  

---
