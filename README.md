# Sales Order Performance Analysis (Power BI)

Ever wondered how much visibility a well-structured BI dashboard can give into sales performance, customer behavior, and operational efficiency?

This project presents a complete end-to-end Sales Order Performance Analysis built in Power BI. The objective was to transform raw transactional sales data into an interactive business intelligence solution that enables strategic decision-making.

The project covers the full analytics workflow, from data ingestion and transformation to data modeling, DAX development, and interactive dashboard design, with an emphasis on performance, usability, and business decision-making.

# Table of Contents

1. [Project Overview](#project-overview)  
2. [Live Interactive Dashboard](#live-interactive-dashboard)  
3. [Business Context](#business-context)  
4. [Project Objectives](#project-objectives)  
5. [Business Questions](#business-questions)  
6. [Dataset Description (Raw Data)](#dataset-description-raw-data)  
7. [Tools & Technologies](#tools--technologies)  
8. [Project Workflow](#project-workflow)  
9. [Key Insights Uncovered](#key-insights-uncovered)  
10. [Strategic Recommendations](#strategic-recommendations)  
11. [Business Impact](#business-impact)  
12. [Limitations](#limitations)  
13. [Challenges Faced](#challenges-faced)  
14. [Conclusion](#conclusion)  
15. [Author](#author)  
16. [Contact](#contact)

## Project Overview

This project delivers a comprehensive Sales Order Performance Analysis using Power BI, transforming raw sales data into a business-ready, interactive dashboard.

## Live Interactive Dashboard

👉 View the interactive dashboard here: [Click to Explore](https://www.novypro.com/profile_about/1768603691117x499853414232449100?Popup=memberProject&Data=1770568818137x550972039693662600)

## Business Context

Sales and operations teams need timely answers to questions such as:

* What is driving revenue growth or decline?

* Which customers, products, and regions contribute the most value?

* Where do operational inefficiencies exist?

* How does sales volume translate into revenue outcomes?

This project addresses these needs by consolidating sales order data into a single, interactive BI solution designed for both strategic and operational analysis.

## Project Objectives

The key objectives of this project were to:

* Analyze overall sales performance trends

* Identify key revenue drivers across products, customers, and warehouses

* Evaluate order fulfillment efficiency

* Enable time-series and comparative analysis

* Build a scalable star schema semantic model

* Deliver a business-ready interactive dashboard

## Business Questions

The analysis was guided by the following questions:

* How is total revenue trending over time?

* Are there periods of abnormal growth or decline?

* Which customer segments contribute the most to revenue?

* Which products and warehouses are top performers?

* How efficient is the order fulfillment process?

What factors most strongly influence revenue performance?

## Dataset Description (Raw Data)

The dataset used in this project consists of raw sales order transaction records, representing individual order lines before any transformation or modeling was applied.

Each row in the dataset represents a single sales order line, containing information related to the order, customer, product, warehouse, and revenue.

| Column Name            | Description                                                       |
| ---------------------- | ----------------------------------------------------------------- |
| **OrderNumber**        | Unique identifier for each sales order                            |
| **OrderDate**          | Date the order was placed                                         |
| **CustomerCode**       | Unique code assigned to each customer                             |
| **CustomerName**       | Name of the customer                                              |
| **Customer Type**      | Classification of customer (Wholesale, Online, Distributor, etc.) |
| **WarehouseCode**      | Code representing the fulfillment warehouse                       |
| **DeliveryName**       | Delivery recipient name                                           |
| **DeliveryRegion**     | Geographic delivery region/state                                  |
| **OrderStatus**        | Status of the order (Completed, Cancelled, etc.)                  |
| **ProductDescription** | Description of the product ordered                                |
| **OrderQuantity**      | Quantity of product ordered                                       |
| **UnitPrice**          | Price per unit of the product                                     |
| **LineTotal**          | Total revenue for the order line (Quantity × Unit Price)          |

### Dataset Characteristics

* Granularity: Order-line level

* Time Coverage: Multi-year transactional data

* Data Type: Structured, transactional sales data

* Revenue Metric: LineTotal serves as the primary revenue field

### Why Transformation Was Required

The raw dataset contained:

* Repeated customer and product attributes

* No dedicated date table for time intelligence

* No separation between fact and dimension entities

To support scalable analysis and performance optimization, the data was transformed into a Star Schema semantic model, with dedicated Order, Customer, and Date dimension tables, and a centralized fact table.

Raw dataset (Sample)

<img width="1366" height="583" alt="01_Raw_Dataset (Sample)" src="https://github.com/user-attachments/assets/077d6060-7da9-43ab-babb-ddab96a75344" />

<img width="398" height="582" alt="02_Raw_Dataset (Sample)" src="https://github.com/user-attachments/assets/4ee185df-59b1-4413-8de9-f6f4ab8efab0" />

**You can access the raw dataset** [here](https://docs.google.com/spreadsheets/d/1vBiwApf93rwRaqN2euEj498mK6Ls-g3Q/edit?usp=sharing&ouid=110710168789266265367&rtpof=true&sd=true)

## Tools & Technologies

* Power BI Desktop

* Power Query

* DAX

* Star Schema Modeling

* Bookmark Navigation

* Data Visualization & Storytelling

## Project Workflow

This project followed a structured, end-to-end Power BI workflow to ensure accuracy, performance, and analytical reliability.

### Data Ingestion

* Imported the raw sales order dataset into Power BI

* Verified column structure, data types, and overall data integrity

### Data Transformation & Preparation

* Transformed the dataset using Power Query

* Ensured correct data type and fixed inconsistent values

* Standardized date formats and categorical fields

* Prepared data for analytical modeling

Data Preparation (Sample)

<img width="1365" height="532" alt="Data Preparation (Sample)" src="https://github.com/user-attachments/assets/6990aa5f-3c70-4df4-99cc-4afd6d7d4e76" />

### Semantic Data Modeling (Star Schema)

To ensure optimal performance and scalability, I:

* Structured the raw transactional data into a centralized Fact Table

<img width="792" height="506" alt="Fact Table (Sample)" src="https://github.com/user-attachments/assets/4e66f45f-11cf-4d48-a7e7-3d66e067625e" />

* Created supporting dimension tables (Order_DIM & Customer_DIM)

<img width="473" height="501" alt="Order_DIM Table (Sample)" src="https://github.com/user-attachments/assets/b466a847-5f79-455d-995d-2c2d8b42c79a" />

<img width="453" height="507" alt="Customer_DIM Table (Sample)" src="https://github.com/user-attachments/assets/065818e2-a881-4192-a1e7-3df02b583365" />

* Built a dedicated Date Table to support time-series and time-intelligence analysis

<img width="351" height="503" alt="Date Table (Sample)" src="https://github.com/user-attachments/assets/998f5032-0b43-438c-9ec4-3a3eb3deb9cd" />

* Modeled the data using a Star Schema, defining clear relationships between fact and dimension tables and applying single-direction filtering to prevent ambiguity

<img width="986" height="529" alt="Data Model" src="https://github.com/user-attachments/assets/a0e979b1-8403-4fb1-9eae-34b13cbb6ba0" />

### Measure Layer Design

* Created a separate table to store all calculated measures

* Centralized business logic for readability, maintenance, and reusability

<img width="226" height="414" alt="Calculated Measures Table (01)" src="https://github.com/user-attachments/assets/5cfa95b2-88ad-44d0-9dc4-3f64a06f38e0" />

<img width="227" height="385" alt="Calculated Measures Table (02)" src="https://github.com/user-attachments/assets/a2270678-7250-4daa-a501-5c52cbfd11ad" />

### DAX Development

Developed optimized DAX measures for:

* Revenue and sales KPIs

* Month-over-Month (MoM) growth

* Time intelligence analysis

* Average Order Value (AOV)

* Operational performance metrics

<img width="642" height="491" alt="DAX Measures (01)" src="https://github.com/user-attachments/assets/6f50fe63-9282-431e-9731-1814b89469b2" />

<img width="638" height="492" alt="DAX Measures (02)" src="https://github.com/user-attachments/assets/1d7c419c-dbd1-4138-999f-f259151c6f60" />

<img width="642" height="492" alt="DAX Measures (03)" src="https://github.com/user-attachments/assets/7adc4fd8-23b7-4201-81a4-913319e03424" />

<img width="643" height="455" alt="DAX Measures (04)" src="https://github.com/user-attachments/assets/a9b09394-c0da-4dfb-88d9-0126cfc7b31b" />

### Dashboard Wireframing

Before building the final dashboard, a structured wireframing approach was used to:

* Define KPI hierarchy

* Establish storytelling flow

* Improve user experience

* Ensure logical visual placement

* Ensured clarity, readability, and executive-level usability.

<img width="1920" height="1080" alt="Overview Wireframe" src="https://github.com/user-attachments/assets/eadeddc1-b6f9-4237-9e05-53341a9f1fb4" />

<img width="1920" height="1080" alt="Performance Wireframe" src="https://github.com/user-attachments/assets/3bad4955-124f-424c-81bb-14f57bfbb655" />

<img width="1920" height="1080" alt="Customer   Region Wireframe" src="https://github.com/user-attachments/assets/206582cf-1e16-40e1-a905-163a07f6ae36" />

### Dashboard Development & Advanced Reporting

#### Key Features:

* Interactive Dashboards: Three tailored pages for different business needs.

* Slicers & Filters: Enabled flexible data exploration to analyze specific segments or timeframes.

* Bookmarks & Custom Navigation: Implemented for advanced reporting and seamless user experience.

#### Dashboard Pages:

This project consists of three interactive dashboards:

* Overview Page

<img width="776" height="437" alt="Overview Page" src="https://github.com/user-attachments/assets/e18a114a-6b92-41a8-80a6-ee8ac7405edd" />

This page is designed for quick decision-making and executive reporting.

* Performance Page

<img width="776" height="439" alt="Performance Page" src="https://github.com/user-attachments/assets/5ac47c93-78eb-403d-9a3c-7c872711445e" />

This page enables operational and performance-focused analysis.

* Customer & Regional Analysis Page

<img width="776" height="438" alt="Customer   Regional Analysis Page" src="https://github.com/user-attachments/assets/2b16bbea-adfb-452e-804a-9158dbe788a5" />

This page supports strategic planning and market expansion decisions.

## Key Insights Uncovered

* Revenue Performance

  * 2020 showed stable and consistent growth

  * A significant revenue decline appeared around mid-2021, indicating a critical risk area

* Customer Analysis

  * Wholesale customers dominate revenue contribution, accounting for ~42% of total sales

* Product & Warehouse Performance

  * Chocolate Truffles emerged as the top revenue-generating product

  * Warehouse AXW921 outperformed all other distribution points

* Operational Efficiency

  * Order Completion Rate remained strong at approximately 95%

* Revenue Drivers

  * Correlation analysis (scatter plot) confirmed a strong relationship between sales volume and revenue

## Strategic Recommendations

Based on the analysis, the following actions are recommended:

* Audit 2021 Revenue Decline
  * Investigate whether the drop was caused by market changes, operational issues, or data reporting gaps.

* Scale the Wholesale Segment
  * Strengthen loyalty initiatives and investigate why the Export channel underperforms.

* Optimize Product Strategy
  * Invest more in high-performing products while reviewing underperforming SKUs.

* Recover Lost Revenue
  * Analyze cancelled and incomplete orders to capture the missing 5%.

## Business Impact

These dashboards enables stakeholders to:

* Monitor performance in real time

* Identify underperforming segments

* Improve operational efficiency

* Support data-driven strategic decisions

* Detect revenue changes early

By consolidating multiple performance perspectives into a single BI solution, the dashboards enhance transparency and responsiveness across the organization.

## Limitations

* Analysis is descriptive, not predictive

* Dataset does not include cost or profit margins

* External economic factors not considered

* Dependent on dataset completeness

Future improvements could include:

* Forecasting models

* Profitability analysis

* Customer lifetime value

* Predictive insights

## Challenges Faced

### Bookmark Configuration for Advanced Navigation

One of the most technically challenging parts of this project was configuring bookmarks correctly for advanced report functionality.

Challenges included:

* Managing visual visibility states properly

* Preventing slicers from resetting unintentionally

* Ensuring bookmarks captured only intended visuals

* Avoiding filter conflicts between pages

* Maintaining consistent user interaction flow

To resolve this:

* I carefully managed the Selection Pane

* Used “Data” option control strategically when saving bookmarks

* Tested interaction states repeatedly to ensure seamless UX

* This process significantly improved my understanding of Power BI’s report layer behavior and interaction control.

### Customer Ranking Using DAX

Creating a dynamic ranking system for customers based on revenue also required careful DAX logic.

Challenges included:

* Ensuring ranking responded dynamically to filters

* Handling ties properly

* Avoiding incorrect ranking due to context transition

* Ensuring ranking worked across different slicer combinations

I implemented a ranking measure using RANKX with proper filter context management to ensure accurate and responsive results.

> These challenges pushed me beyond surface-level dashboard development and deepened my technical control over Power BI’s modeling and reporting layers.

## Conclusion

Working on this project significantly strengthened my Power BI skills end-to-end, from data ingestion and transformation, to building a solid data model for performance and usability, writing efficient DAX measures the smart way, developing interactive dashboards, and using bookmarks to add advanced report functionality.

This project demonstrates the ability to:

* Build scalable semantic models

* Develop optimized DAX measures

* Design executive-ready dashboards

* Deliver business-focused analytical solutions

## Author
Ibrahim Abdulrasaq | Data Analyst | BI Analyst

## Contact

If you’d like to discuss this project or collaborate on data analytics work, feel free to connect.

🔗 [Email](mailto:ibrahimabdulrasaqademola2017@gmail.com)

🔗 [LinkedIn](https://www.linkedin.com/in/ibrahim-abdulrasaq/)

🔗 [Github](https://github.com/ibrahimabdulrasaq)
