<!-- =========================
Ferns & Petals Sales Analysis
========================== -->

<h1 align="center"> 🌸🎁 Ferns & Petals — Sales Analysis 📊✨ (Excel) 🌿💐</h1>

<p align="center">
  End-to-end retail sales analytics project in <b>Microsoft Excel</b> - from ETL (Power Query) to data modeling (Power Pivot), analysis, and an interactive dashboard.
</p>

<p align="center">
  <a href="#"><img alt="Tool" src="https://img.shields.io/badge/Tool-Microsoft%20Excel-217346"></a>
  <a href="#"><img alt="ETL" src="https://img.shields.io/badge/ETL-Power%20Query-6CC24A"></a>
  <a href="#"><img alt="Modeling" src="https://img.shields.io/badge/Data%20Model-Power%20Pivot-FFD54F"></a>
  <a href="#"><img alt="Output" src="https://img.shields.io/badge/Deliverable-Interactive%20Dashboard-FF8A65"></a>
</p>

---

## Table of contents
- [Business context](#business-context)
- [Project objectives](#project-objectives)
- [Deliverables](#deliverables)
- [Data](#data)
- [Workflow (BI lifecycle)](#workflow-bi-lifecycle)
- [Dashboard preview](#dashboard-preview)
- [Key metrics (dataset summary)](#key-metrics-dataset-summary)
- [Key insights](#key-insights)
- [How to use](#how-to-use)
- [Repository structure](#repository-structure)
- [Tools & skills](#tools--skills)
- [Author](#author)

---

## Business context
Ferns & Petals is a gifting brand selling cakes, flowers, plants, and personalized gifts. This project addresses common retail analytics gaps such as unclear sales trends across time/cities/categories, limited visibility into top products & occasions, and delivery-time variability impacting customer experience.

## Project objectives
- Identify revenue drivers across **categories**, **products**, **cities**, and **occasions**.
- Understand customer behavior using **gender-wise** and city-wise segmentation.
- Track operational performance through **delivery days** and order timing patterns.
- Convert raw transactional data into an Excel dashboard and a business-ready report.

## Deliverables
- `Ferns_and_Petals_Sales_Analysis.xlsx` (interactive dashboard + data model)
- `Ferns & Petals Sales Analysis Report.pdf` (insights + recommendations)
- `Problem Statement.pdf`
- Raw datasets: `customers.csv`, `orders.csv`, `products.csv`

## Data
### Source files
| File | Description | Key columns |
|------|-------------|------------|
| `customers.csv` | Customer master data | `Customer_ID`, `Name`, `City`, `Gender` |
| `products.csv` | Product catalog | `Product_ID`, `Category`, `Price` |
| `orders.csv` | Transactions | `Order_ID`, `Customer_ID`, `Product_ID`, `Quantity`, `Order_Date`, `Delivery_Date` |

### Core derived fields (Power Query)
- `Delivery Days` = Delivery_Date − Order_Date  
- `Revenue` = Price × Quantity  
- `Profit Margin` (as defined in the workbook model)

## Workflow (BI lifecycle)
1. **Extract**: Imported all CSVs into Power Query.
2. **Transform (ETL)**: Removed duplicates/blanks, standardized data types, cleaned categorical columns (occasion/category/city), and added derived fields.
3. **Model**: Built a **star schema** in Power Pivot:
   - Fact: `Orders`
   - Dimensions: `Customers`, `Products`
   - Relationships via `Customer_ID` and `Product_ID`
4. **Analyze**: Pivot Tables + DAX measures for revenue, orders, AOV, and delivery metrics.
5. **Visualize**: Interactive dashboard with KPI cards, charts, and slicers.
6. **Report**: PDF report with findings and business recommendations.

## Dashboard preview
![Dashboard](dashboard_image.png)

## Key metrics (dataset summary)
| Metric | Value |
|--------|------:|
| Total Orders | 15 |
| Unique Customers | 99 |
| Unique Products | 15 |
| Total Revenue | ₹17,691 |
| Average Revenue per Order | ₹1,179 |
| Average Delivery Days | ~6.2 days |

## Key insights
### Top cities by revenue
- Rajkot
- Bilaspur
- Jaipur
- Bardhaman
- Ambala

### Top categories by revenue
- Colors
- Sweets
- Cake
- Plants
- Mugs

### Occasion performance (high to moderate)
1. Diwali (highest revenue)
2. Anniversary (consistent demand)
3. Birthday (high order volume)
4. Valentine’s Day (seasonal spike)
5. Holi (moderate revenue)

### Customer & operations notes
- Female customers generated slightly higher revenue; male customers placed more orders with lower AOV.
- Average delivery time is ~5.5 days, indicating a clear operational improvement opportunity.
- Peak sales months observed: February, July, and September.
- Orders were most frequently placed during evening hours.

## How to use
1. Download or clone the repository.
2. Open `Ferns_and_Petals_Sales_Analysis.xlsx` in Microsoft Excel (Desktop).
3. If prompted, enable content and refresh queries:
   - **Data** → **Refresh All**
4. Use slicers/filters to explore performance by city, category, occasion, and customer attributes.

## Repository structure
```text
Ferns-and-Petals-Sales-Analysis/
│
├── data/
│   ├── customers.csv
│   ├── products.csv
│   └── orders.csv
│
├── Ferns_and_Petals_Sales_Analysis.xlsx
├── Ferns & Petals Sales Analysis Report.pdf
├── Problem Statement.pdf
├── dashboard_image.png
└── README.md
