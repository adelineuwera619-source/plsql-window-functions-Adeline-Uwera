# Financial Data Analysis with SQL Window Functions
Step 1: Problem Definition
**Business Context**  
TechFinance Ltd. is a mid-sized IT services company based in Kigali, Rwanda. The Finance Department manages customer accounts, monitors sales performance, and tracks operational costs. With increasing competition in the IT sector, the company needs stronger financial insights to maintain profitability.  

**Data Challenge**  
The company’s financial data is spread across multiple sources — customer profiles, product catalogs, and sales transactions. This separation makes it difficult to track performance across time, identify top customers, and detect financial risks. As a result, decision-making is slow and often based on incomplete information.  

**Expected Outcome**  
By consolidating financial data and applying advanced analytics, TechFinance expects to gain deeper insights into its revenue streams. The company aims to identify top customers and products, measure month-to-month growth, and segment clients by spending patterns. These insights will improve financial planning, guide marketing, and support long-term growth.  

---

 Step 2: Success Criteria
The project will be considered successful if the following measurable goals are achieved:  
1. Identify the **Top 5 products per region/quarter** using `RANK()`.  
2. Calculate **running monthly sales totals** with `SUM() OVER()`.  
3. Measure **month-over-month growth** using `LAG()` / `LEAD()`.  
4. Segment customers into **quartiles** using `NTILE(4)`.  
5. Compute **3-month moving averages** of sales using `AVG() OVER()`.  

---

 Step 3: Database Schema
 Tables  

| Table        | Purpose              | Key Columns                              | Example Row                          |  
|--------------|----------------------|-------------------------------------------|--------------------------------------|  
| **customers** | Stores customer info | `customer_id (PK)`, `name`, `region`      | 1001, John Doe, Kigali               |  
| **products**  | Product catalog      | `product_id (PK)`, `name`, `category`     | 2001, Coffee Beans, Beverages        |  
| **transactions** | Sales records     | `transaction_id (PK)`, `customer_id (FK)`, `product_id (FK)`, `sale_date`, `amount` | 3001, 1001, 2001, 2024-01-15, 2500 |  

**ER Diagram:**  
- **customers** (1-to-many) → **transactions**  
- **products** (1-to-many) → **transactions**  

---
 Step 4: Window Functions Implementation
### 4.1 Ranking Functions  
Use case: Top customers by revenue (`ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `PERCENT_RANK()`).  
**Interpretation:** Highlights top-performing customers and their ranking distribution.  

### 4.2 Aggregate Functions  
Use case: Running totals and sales trends (`SUM()`, `AVG()`, `MIN()`, `MAX()`).  
**Interpretation:** Tracks cumulative sales, moving averages, and identifies highs and lows in performance.  

### 4.3 Navigation Functions  
Use case: Month-over-month growth (`LAG()`, `LEAD()`).  
**Interpretation:** Compares current and previous months to measure growth percentages.  

### 4.4 Distribution Functions  
Use case: Customer segmentation (`NTILE(4)`, `CUME_DIST()`).  
**Interpretation:** Divides customers into spending tiers for targeted strategies.  

---
Step5: Results Analysis
**Descriptive – What happened?**  
A small group of customers contributed the majority of revenue. Sales generally grew but showed occasional monthly declines.  

**Diagnostic – Why?**  
High-value customers and premium products drove revenue. Fluctuations were caused by seasonal demand, promotions, and regional variations.  

**Prescriptive – What next?**  
Focus on retaining high-value customers, expand loyalty programs for mid-tier clients, and introduce promotions in low-demand periods to stabilize revenue.  

---
Step 6: References
1. PostgreSQL Documentation – Window Functions  
2. SQL Server Documentation – Ranking Functions
3. TutorialsPoint – Advanced SQL Queries   

---

