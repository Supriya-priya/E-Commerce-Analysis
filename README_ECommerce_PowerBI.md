
# 📊 E-Commerce Sales & Profit Analysis Dashboard – Power BI

This repository contains an interactive Power BI dashboard that offers deep insights into e-commerce performance metrics such as sales, orders, and net profit. The project showcases effective use of MySQL, Power BI, DAX, and data visualization techniques to empower decision-making.

🔗 **Live Dashboard**: [Click here to view](https://app.powerbi.com/groups/me/reports/caafebd7-5d0a-48aa-bb36-38863292ae51/0af890d8e46708602895?experience=power-bi&bookmarkGuid=a402f9fac498fa6893c5)

---

## 🔧 Project Setup & Data Connection

### 1. Connect to MySQL Database
- Ensure your sales dataset is available in **MySQL**.
- Create a **view** to filter/prepare your data for reporting.

### 2. Load Data into Power BI
- Open **Power BI Desktop**.
- Go to: `Get Data` → `More` → `Database` → `MySQL`.
- Provide server/database credentials and connect to the MySQL view.

---

## 📈 Dashboard Page 1: Sales & Net Profit Analysis

### ✅ Key Metrics with DAX Cards
- **Total Sales**
- **Unique Orders**
- **Avg. Sales per Order**

```DAX
Average Sales Value per Order = 
SUM('classicmodelss sales_data_for_power_bi'[cost_of_sales]) / 
DISTINCTCOUNT('classicmodelss sales_data_for_power_bi'[orderNumber])
```

### 🌍 Grouping by Region
- **Group 1**: USA  
- **Group 2**: All other countries (labeled "Rest of the World")

### 📉 Trend Analysis with Line Charts
- Sales Over Time
- Orders Over Time
- Avg. Order Value Over Time  
(Use `Order Date` with hierarchy set to Year, Quarter, and Month)

### 🔘 Toggle Between Sales & Net Profit (Using Bookmarks)
1. Create a control table:
   | Number ID | Control       |
   |-----------|----------------|
   | 1         | Sales          |
   | 2         | Net Profit     |

2. DAX Measure for Toggling:
```DAX
Selected Metric = 
SWITCH(
  SELECTEDVALUE('Table'[Number Id]), 
  1, SUM('classicmodelss sales_data_for_power_bi'[sales_value]),
  2, SUM('classicmodelss sales_data_for_power_bi'[sales_value]) - SUM('classicmodelss sales_data_for_power_bi'[cost_of_sales]),
  SUM('classicmodelss sales_data_for_power_bi'[sales_value])
)
```
3. Create slicers, pill-shaped toggle buttons, and bookmarks (`Select 1`, `Select 2`) to dynamically switch metrics.

### 📊 Supporting Visualizations
- **Stacked Bar Chart**: Sales/Profit by Country
- **Scatter Plot**: Sales vs Cost/Profit
- **Top Countries by Orders**: Column Chart
- **Donut Chart**: Sales/Profit Distribution by Country

### 🧠 Dynamic Titles for Visuals
- Enable title → click `fx` → link to `Control` table value for dynamic titles.

### 🧾 Filters
- **Order Date Slicer**
- **Product Name Slicer**

---

## 📊 Dashboard Page 2: Net Profit Decomposition + Sales Overview

### 🌳 Decomposition Tree
- Visualize Net Profit broken down by:
  - Country
  - Product Line
  - Customer Name

### 📋 Sales Summary Table
- Columns:
  - Year, Month
  - Sales Value
  - Month-over-Month Change (%)
  - Year-to-Date Sales

#### 🧮 Quick Measures Used:
- **MoM % Change** – formatted as % in the model.
- **YTD Sales** – using built-in Power BI time intelligence functions.

### 🔀 Page Navigation
- Add `Page 1` and `Page 2` navigation buttons.
- Enable action → set to `Page Navigation` → link to appropriate page.
- Use `Ctrl + Click` to switch during report view.

---

## 🖼️ Dashboard Snapshots

| Page 1: Overview | Page 2: Profit Analysis |
|------------------|-------------------------|
| ![Page 1](https://github.com/pradeeshculer/E-Commerce-Analysis/assets/115096109/30b374ef-2a55-428d-8b48-380688c2896c) | ![Page 2](https://github.com/pradeeshculer/E-Commerce-Analysis/assets/115096109/933822bc-befd-43a7-94c8-5a213a42841f) |

---

## 🎯 Conclusion

This Power BI project demonstrates a comprehensive approach to analyzing e-commerce data, offering:
- Real-time insights into sales performance
- Regional breakdowns and profitability metrics
- Drill-down capabilities and dynamic filtering

> Whether you're a business stakeholder or a data enthusiast, this dashboard provides the tools needed to make data-driven decisions effectively.

---

## 📁 Project Structure

```
E-Commerce-Analysis/
│
├── 📁 PowerBI_Files/
│   └── ecommerce_dashboard.pbix
│
├── 📁 MySQL_Scripts/
│   └── create_sales_view.sql
│
├── 📁 Screenshots/
│   ├── dashboard_page1.png
│   └── dashboard_page2.png
│
└── README.md
```

---

## 📬 Feedback & Contributions

Have suggestions or want to collaborate? Feel free to open an issue or submit a pull request. Let's grow and build better dashboards together!
