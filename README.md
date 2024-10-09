# AtliQ Hardware Ad Hoc Insights

## About Company
AtliQ Hardware (Imaginary Company) is a global leader in hardware manufacturing, offering a diverse range of products across three main categories: peripherals & accessories, personal computers, and network storage. Our customer base is broadly classified into three groups: retailers, direct consumers, and distributors.

## Background
Write SQL Queries for providing insights to make quick and smart data-informed decisions as per Product Manager need.

## Database
MySQL

## Dataset
**gdb0041**
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
