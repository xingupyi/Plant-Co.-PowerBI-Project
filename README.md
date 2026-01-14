# Plant Co. Sales Performance Dashboard (Power BI)

## Project Overview

This project analyses **Plant Co.’s sales performance** across products, accounts, countries, and time using Power BI to support year-to-date performance tracking, profitability analysis, and comparison against prior year results.

---

## Data Modelling Approach

The data model is designed using a **star schema**. At the centre of the model is the `Fact_Sales` table, which stores transaction-level metrics such as sales value, cost of goods sold, quantity, price, and transaction date. This fact table acts as the single source for all quantitative analysis.

Surrounding the fact table are multiple dimension tables. `Dim_Product` captures the product hierarchy, allowing analysis at the family, group, and individual product levels, as well as by product attributes such as type and size. `Dim_Accounts` contains customer and geographic information, enabling country-level and account-level analysis. `Dim_Date` provides a dedicated calendar table that supports time intelligence calculations such as year-to-date (YTD) and prior year-to-date (PYTD), while also preventing future dates from impacting analysis.

In addition to core dimensions, a dedicated `_Measure` table is used to centralise DAX measures, improving model organisation and maintainability. A small helper table, `Slc_values`, supports slicer-driven metric selection within the report. Relationships are defined as one-to-many from each dimension table to the fact table, with single-direction filtering to maintain clarity and avoid ambiguity. This modelling approach ensures accurate calculations, reusable measures, and consistent behaviour across visuals.

<img width="2024" height="848" alt="image" src="https://github.com/user-attachments/assets/f8efd997-2021-44c6-96ec-9382e675b00a" />

---

## Dashboard Description
To analyse the performance of Plant Co. 3 most relevant KPIs were identified as:
1.Gross profit: takes into account COG to reveal what/where/when is most profitable
2.Quantity: amount of goods sold what/when/where
3.Sales: revenue of goods sold what/when where

In order to visualise the "when", a water graph was selected to compare the relevant statistics (depending on slicer) by month YTD vs PYTD. For the "what", a scattered chart was used. For the "where", a treemap with the breakdown by region was used.
<img width="1986" height="1114" alt="image" src="https://github.com/user-attachments/assets/451fd323-5141-4aca-a378-b5baf09178ca" />


