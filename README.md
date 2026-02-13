# Sales Performance Analytics | End-to-End Power BI Implementation

# Executive Summary
This project transforms raw transactional sales data into a scalable, enterprise-grade Power BI solution.
The focus was shifted from simple visualization to building a high-performance Star Schema architecture capable
of supporting complex time-intelligence and year-over-year (YoY) growth analysis.

# Data Architecture & Modeling
The core of this implementation is a Star Schema designed to optimize the VertiPaq engine and ensure filter context integrity.

1. Data Transformation (Power Query)
Schema Enforcement: Standardized data types across all fields to prevent aggregation errors and optimize memory storage.

Normalization: Deconstructed the flat CSV structure into distinct Fact and Dimension tables to eliminate redundancy.

Integrity Checks: Implemented duplicate removal on primary keys (ProductCode, CustomerName, Date) to guarantee one-to-many relationship validity.

2. Dimensional Modeling
Fact Table: Fact_Sales (Granularity: Order Line Level).

Dimensions: Dim_Date, Dim_Product, Dim_Customer, Dim_Geography.

Relationship Logic: One-to-many (1:*) relationships with single-direction cross-filtering to maintain predictable DAX behavior and avoid circular dependencies.

# Analytical Logic (DAX)
Calculations were developed using a layered approach, separating base measures from advanced business logic.

Core Metrics: Total Revenue, Volume, and Margin analysis based on MSRP vs. Transactional Price.

Time Intelligence: Implementation of YTD, QTD, and LY (Last Year) measures to enable period-over-period growth tracking.

Ranking & Pareto: Dynamic ranking of Top 10 Customers and Products to identify revenue concentration.

# Dashboard Strategy
The UI/UX is structured using a Top-Down Analytical Flow:

Strategic Layer: High-level KPI cards for immediate performance awareness (Revenue, Quantity, Avg. Discount).

Tactical Layer: Trend lines and YTD vs. LY comparisons to identify seasonal shifts.

Operational Layer: Granular breakdowns by Territory, Product Line, and Deal Size for deep-dive root cause analysis.

# Business Impact
The final model is designed to answer critical commercial questions:

Growth Tracking: What is our current YTD trajectory vs. the previous fiscal year?

Revenue Concentration: Which top 5% of customers are driving the majority of sales?

Territory Performance: Identifying underperforming regions relative to their historical averages.

# Tech Stack
Power BI Desktop (Modeling & Visualization)

Power Query / M (ETL)

DAX (Analytical Measures)

Star Schema (Data Architecture)
