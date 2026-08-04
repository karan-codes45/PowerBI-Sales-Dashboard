<img width="584" height="53" alt="image" src="https://github.com/user-attachments/assets/efbcb9ac-ea0f-4fac-b4f5-9a661bdeaf27" /># 📊 E-Commerce Sales Analytics Dashboard

An end-to-end **Power BI** portfolio project analyzing Indian e-commerce sales data — from raw CSVs to a governed star-schema data model to a 3-page interactive dashboard with drillthrough and DAX-powered KPIs.

---

## 🎯 Business Objective

Indian e-commerce companies generate huge volumes of order-level data but struggle to convert it into fast, decision-ready insight for leadership, category, and operations teams. This project builds a Power BI solution to:

- Track revenue, order volume, and monthly trends
- Understand product mix — top categories, brands, and customer segments
- Monitor operations — warehouse performance, delivery time, shipping cost, returns
- Enable self-service analysis via region/date slicers, without touching raw data

---

## 🗂️ Data Model — Star Schema

| Table | Key Fields |
|---|---|
| **Fact_Sales** | OrderID, Quantity, TotalBill, ReturnFlag, IsFestiveSale, DeliveryDays, ShippingCost |
| **Dim_Date** | Date, Month, Year, Quarter |
| **Dim_Product** | Category, Brand, Product Name |
| **Dim_Customer** | CustomerID, Segment |
| **Dim_Region** | Region, State, Warehouse |
| **Dim_Payment** | PaymentMethod |

One fact table connected to four dimension tables — built for clean, fast DAX and easy slicing by date, region, product, and payment method.

---

## 📄 Dashboard Pages

### 1️⃣ Executive Sales Overview
![Executive Sales Overview](Dashboards/Executive%20Sales%20Dashboard.jpg)

**Key metrics:** ₹156.64M Total Revenue · 6K Orders

**Insights:**
- West and North regions together drive over half of total revenue, led by West at ~₹42M
- UPI is the dominant payment method at 36.76% of revenue, ahead of Wallet and Net Banking
- Electronics alone contributes close to 90% of category revenue — a heavy category concentration
- Only 13.93% of orders are festive-sale, yet the monthly trend still peaks sharply around Oct–Nov

### 2️⃣ Product Performance
![Product Performance](Dashboards/Product%20Performance.jpg)

**Key metrics:** ₹26.11K Avg Order Value · 45.1% Regular Segment share

**Insights:**
- Boat leads brand-wise revenue at ~₹20M, followed by Xiaomi, Noise, and Realme
- Electronics dominates the category revenue funnel at 96.63%
- Regular customers generate 45.11% of revenue, with Premium customers close behind at 32.72%
- By units sold, Nike is the top-selling brand, well ahead of Roadster and Penguin

### 3️⃣ Operations Dashboard
![Operations Dashboard](Dashboards/Operations%20Dashboard.jpg)

**Key metrics:** 6 days Avg Delivery · 9,108 units tracked

**Insights:**
- Kolkata warehouse leads throughput at ~₹23M, with Delhi trailing all listed warehouses
- Customer rating and delivery days move inversely from North to South
- West region carries the highest shipping cost, despite also being the top revenue region
- Fashion has the highest return count (251 units) among returned orders

---

## 🧮 Key DAX Measures

```DAX
Total Revenue = SUM(Fact_Sales[TotalBill])

Festive Sales % =
DIVIDE(
    CALCULATE([Total Revenue], Fact_Sales[IsFestiveSale] = "Yes"),
    [Total Revenue]
)

Avg Order Value =
DIVIDE([Total Revenue], DISTINCTCOUNT(Fact_Sales[OrderID]))

Return Rate % =
DIVIDE(
    CALCULATE(SUM(Fact_Sales[Quantity]), Fact_Sales[ReturnFlag] = "Yes"),
    SUM(Fact_Sales[Quantity])
)
```

---

## 🛠️ Tools & Techniques

- **Power BI Desktop** — data modeling, DAX, report design
- **Power Query** — data cleaning and transformation
- **Star Schema modeling** — fact and dimension table design
- **DAX** — calculated measures for KPIs and percentage breakdowns
- **Interactive features** — page navigation buttons, date/region slicers, drillthrough

---

## 📁 Files in this Repository

| File | Description |
|---|---|
| `e_com_express.pbix` | Full Power BI project file (open in Power BI Desktop) |
| `Dashboards/Executive Sales Dashboard.jpg` | Screenshot — Page 1 |
| `Dashboards/Product Performance.jpg` | Screenshot — Page 2 |
| `Dashboards/Operations Dashboard.jpg` | Screenshot — Page 3 |
| `E-Commerce_Sales_Dashboard_Portfolio.pptx` | Presentation deck summarizing the project |

---

## 👤 Author

**Karan Pawar**
B.Sc. Computer Science | PowerBI Devloper & Data Analyst

- GitHub: [github.com/karan-codes45](https://github.com/karan-codes45)
- LinkedIn:(https://www.linkedin.com/in/karan-pawar-9a645a2ab)
<img width="584" height="53" alt="image" src="https://github.com/user-attachments/assets/718efb77-bd0a-459e-a06e-6291868c2f4d" />
