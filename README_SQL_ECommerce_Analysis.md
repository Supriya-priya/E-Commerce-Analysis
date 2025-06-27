
## 🛠️ SQL-Based E-Commerce Data Analysis

This section highlights the analytical approach and business insights derived using advanced SQL queries on the e-commerce dataset. The objective was to transform raw transactional data into valuable intelligence that supports strategic decisions across sales, credit, logistics, and customer engagement.

---

### 🎯 Objectives of the Analysis

1. **Customer Credit Limit Overview**  
   - Retrieve customer credit limits to assess financial exposure and monitor potential risks.

2. **Late Shipment Identification**  
   - Detect orders that were delivered past the required date to identify operational inefficiencies.

3. **Credit Limit Breach Detection**  
   - Find customers whose purchases exceed their credit limits, helping flag credit risk and ensure payment follow-ups.

4. **Sales Distribution by Region**  
   - Analyze office-wise sales performance broken down by customer country to uncover geographic trends.

5. **Product Bundling Trends**  
   - Discover which products are frequently purchased together to enhance cross-selling and merchandising strategies.

6. **Country-Wise Sales Summary**  
   - Provide aggregated sales performance by country to support strategic planning and resource allocation.

7. **Order-to-Order Sales Value Change**  
   - Track how the sales value changes from one order to the next for each customer, helping spot positive or negative sales trends.

---

### 🧠 SQL Concepts Utilized

- **Common Table Expressions (CTEs)**  
  Used to modularize queries and improve readability for multi-step transformations.

- **Subqueries**  
  Helped isolate intermediate calculations or filters inside larger queries.

- **INNER JOINs**  
  Integrated data from multiple related tables such as orders, customers, and offices.

- **CASE Statements**  
  Applied conditional logic to categorize data or create computed fields.

- **ROW_NUMBER() Window Function**  
  Assigned sequential ordering to enable comparisons like current vs. previous order values.

- **GROUP BY & Aggregates**  
  Used for summarizing sales and credit data by relevant dimensions like country or customer.

---

### 📌 Key Insights Uncovered

- **Credit Risk Awareness**: Monitoring credit limits and identifying customers who exceed them improves financial governance.
- **Logistics Optimization**: Analyzing delays in delivery reveals gaps in operational efficiency.
- **Regional Performance Metrics**: Comparing sales across countries and offices offers insights into market potential and regional demand.
- **Sales Growth Tracking**: By comparing order values over time, we can detect upward or downward trends in customer purchases.
- **Bundling & Inventory**: Identifying products frequently bought together supports bundling promotions and smarter inventory planning.

---

### ✅ Conclusion

This SQL-based analysis extracts meaningful patterns from complex e-commerce data. By using advanced SQL techniques, we gained actionable insights across financial, operational, and sales dimensions. These findings not only support more informed decision-making but also enhance business efficiency, reduce credit exposure, and improve customer satisfaction.

> The full SQL queries and logic behind each insight are available in the `SQL_Queries/` folder of this repository.
