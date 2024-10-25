# AtliQ Hardware Ad Hoc Insights
- **Domain** - Consumer Goods
- **Function** - Executive Management
- I built this project by following the [Codebasics SQL Course](https://codebasics.io/courses/sql-beginner-to-advanced-for-data-professionals) </br>
- [Linkedin Post](https://www.linkedin.com/feed/update/urn:li:activity:7249848937300299777/)
## About Company
AtliQ Hardware (Imaginary Company) is a global leader in hardware manufacturing, offering a diverse range of products across three main categories: peripherals & accessories, personal computers, and network storage. Our customer base is broadly classified into three groups: retailers, direct consumers, and distributors.

## Background
Write SQL Queries for providing insights to make quick and smart data-informed decisions as per Product Manager needs.

## Database
MySQL

## Dataset
**gdb0041**- main data source
- **Tables**:
  - _dim_customer_ : customer_code, customer, platform, channel, market, sub_zone, region
  - _dim_product_ : product_code, division, segment, category, product, variant
  - _fact_forecast_monthly_ :  date, fiscal_year, product_code, customer_code, forecast_quantity
  - _fact_freight_ : market, fiscal_year, freight_pct, other_cost_pct
  - _fact_gross_price_ : product_code, fiscal_year, gross_price
  - _fact_manufacturing_cost_ : product_code, cost_year, manufacturing_cost
  - _fact_post_invoice_deductions_ : customer_code, product_code, date, discount_pct, other_deductions_pct
  - _fact_pre_invoice_deductions_ : customer_code, fiscal_year, pre_invoice_discount_pct
  - _fact_sales_monthly_ : date, fiscal_year, product_code, customer_code, sold_quantity
    
- **Genearated Table**:
  - _dim_date_ : calendar_date, fiscal_year
  - _fact_act_est_ : date, fiscal_year, product_code, customer_code, sold_quantity, forecast_quantity
 
- **Functions**
    - get_fiscal_year
 ![](https://github.com/user-attachments/assets/2848df54-88a2-4e0c-bda5-5d545e6ac05e)
- **Views**
  - net_sales
    - ![net_sales](https://github.com/user-attachments/assets/ac2d7ad8-ff1d-494a-adc8-ce6211e64add)
  - gross_sales
    - ![gross_sales](https://github.com/user-attachments/assets/ffd95e2e-2a60-48de-8daa-3de02b9155ed)
  - sales_postinv_discount
    - ![sales_post_inv_dist](https://github.com/user-attachments/assets/2b8f698b-0415-47b0-9555-1e54ad567cac)
  - sales_preinv_discount
    - ![sales_pre_inv_dist](https://github.com/user-attachments/assets/dbeab807-b7bd-4bc5-973e-bd41c70c2b76)

## Steps Taken:
  - Created necessary function like get_fiscl_year to reduce query duration/ fetch time.
  - Created various views (net_sales, gross_sales etc) and Generated tables like dim_date, fact_act_est to avoid repetation and query duration/ fetch time.
  - Created stored procedures for reuseability and better access control over data.
  - Used triggers for automatic data updation for fact_sales_monthly & fact_forecast_monthly.

## Queries:
  - Generate a report of individual product sales (aggregated on a monthly basis at the product level) for Croma India customers for FY 2021
  - Generate Croma India Sales report on yearly basis
  - Create Stored Procedure to get gross monthly total sales report by Customer
  - Create stored procedure that can determine the market badge based on the following logic {If total sold quantity > 5 million that market is considered Gold else it is Silver}
  - Write Stored Procedure for generating report for top markets, products, customers by net sales for a given financial year to get an holistic view of financial performance and to take appropriate actions to address any potential issues.
  - Generate Customers net sales % share report for FY 2021
  - Create Stored Procedure to get top n products in each division by their quantity sold as per Fiscal Year
  - Create an aggregate forecast accuracy report for all the customers for a given fiscal year to track forecast accuracy by customer
  - Generate a report for Supply Chain Manager for identifying customers whose forecast accuracy has dropped from FY 2020 to 2021

## Report
[Ad HOC INSIGHTS](https://github.com/shellynagar27/Consumer-Goods---Ad-Hoc-Analysis/blob/main/Ad%20HOC%20INSIGHTS.pdf)

## Key learnings
  - Concept of query optimisation and how to use **Explain Analyze** for better understanding of query duration and fetch time
  - Storage optimisation by identifying correct datatype for each field of dataset
  - Concepts of joins (left, right, full join), union & union all
  - Difference between sub Query & co-related sub query
  - Basics of Database design and steps involved in it
  - Creation of ERD diagrams and how to establish relationship between various tables using primary and foreign key
  - Concept of Data Integrity, Normalisation and link tables
  - Creation of generated columns, user defined functions, triggers and events.
  - Creation of CTEs, Stored Procedure, Views, Temporary table and about their readability, validity, and usability
  - How to set account privileges for better data protection
  - When to use **Index** functionality for speeding up sql queries

## Other tools used
  - [Canva](https://www.canva.com/)
  - [Flaticon](https://www.flaticon.com/)
