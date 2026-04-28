## Power_BI_Sales_Project
# 📊 Sales & Business Intelligence Dashboard — Power BI Project

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue?style=for-the-badge)
![Data Model](https://img.shields.io/badge/Data%20Model-Star%20Schema-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Live%20%7C%20Web%20Embedded-brightgreen?style=for-the-badge)

> A multi-page interactive Power BI dashboard built to analyze sales performance, regional distribution, product trends, and customer insights — with full web embed capability via Power BI Service.

---

## 🔗 Live Demo

> 🌐 This report has been published and embedded on the web via **Power BI Service**.  
> You can view the live, interactive version here: **[→ View Embedded Report](#)** *(replace with your embed link)*

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dashboard Pages](#-dashboard-pages)
- [Data Model](#-data-model)
- [Key Metrics & DAX Measures](#-key-metrics--dax-measures)
- [Tools & Technologies](#-tools--technologies)
- [How to Embed in a Website](#-how-to-embed-in-a-website)
- [How to Run Locally](#-how-to-run-locally)
- [Skills Demonstrated](#-skills-demonstrated)

---

## 📋 Project Overview

This project is a fully interactive Business Intelligence dashboard developed in **Microsoft Power BI Desktop**. It connects multiple dimension and fact tables in a **star schema** data model and delivers visual insights across four analytical dimensions:

| Dimension | Description |
|---|---|
| 💰 Sales Performance | Overall revenue, profit, and margin KPIs |
| 🌍 Regional Analysis | Geographic breakdown of sales by country and city |
| 📦 Product Analysis | Top-selling products and category mix |
| 👥 Customer Insights | Individual customer revenue and profit margin contribution |

The report was built with a recruiter-ready, executive-level aesthetic — clean cards, interactive slicers, and cross-filtered visuals — and published via **Power BI Service** for web embedding.

---

## 📄 Dashboard Pages

The report contains **4 pages**, each focused on a specific analytical lens:

---

### 1. 🏠 Dashboard (Main Overview)

The landing page provides a high-level summary of business performance through KPI cards and interactive charts.

**Visuals included:**

| Visual Type | Title / Metric |
|---|---|
| 📋 KPI Card | **Total Sales** — Total Revenue measure |
| 📋 KPI Card | **Profit Margin %** — Calculated profit margin |
| 📋 KPI Card | **Total Profit** — Sum of Profit |
| 📊 Bar Chart | **Total Sales by Product** — Revenue by product name |
| 🍩 Donut Chart | **Total Sales by Country** — Revenue distribution across countries |
| 📈 Line Chart | **Total Profit & Revenue by Profit Margin** — Trend correlation |
| 🥧 Pie Chart | **Sales by Product Category** — Category-level USD sales |
| 🎛️ Slicer | Filter by **Country** |
| 🎛️ Slicer | Filter by **Product Category** |

> **All visuals are cross-filtered** — clicking any data point dynamically updates all other visuals on the page.

---

### 2. 🗺️ Regional Analysis

An interactive map-driven page that allows geographic drill-down into sales performance.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 🗺️ Esri ArcGIS Map | **Sales by Country & Region** — Plotted by Total Revenue |
| 🎛️ Slicer | Filter by **City** |

> Uses **Esri ArcGIS Maps** integration within Power BI for rich geographic visualization. Revenue values are mapped as bubble sizes across countries and regions.

---

### 3. 📦 Product Analysis

A dedicated page for deep-diving into product-level performance.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 🌳 Treemap | **Sales by Product Name** — USD Total Sales weighted by area |
| 🎛️ Slicer | Filter by **Product Category** |

> The treemap makes it immediately clear which products drive the most revenue through visual weighting.

---

### 4. 👥 Customer Insights

Customer-level analysis that connects revenue contribution to profitability.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 📊 Combo Chart (Line + Column) | **Revenue & Profit Margin by Customer** — dual-axis combo chart |
| 🎛️ Slicer | Filter by **Customer Name** |

> This combo chart overlays **Total Revenue** (columns) with **Profit Margin** (line) per customer — allowing easy identification of high-revenue but low-margin customers.

---

## 🗄️ Data Model

The project uses a **Star Schema** with one central fact table and three dimension tables:

```
Dim_Products ──────────┐
                        │
Dim_Date ──────────────┼──► Facts_Table (Central Fact Table)
                        │
Dim_Customers ─────────┘
```

### Tables & Key Columns

#### `Facts_Table` *(Fact Table)*
Central table containing all transactional sales data.

| Column | Description |
|---|---|
| `SalesAmount` | Raw sales amount |
| `Total Revenue` | Calculated revenue measure |
| `Profit` | Profit per transaction |
| `ProfitMargin` | Margin as a ratio |
| `USD_Total Sales` | Revenue normalized to USD |

#### `Dim_Products` *(Dimension)*

| Column | Description |
|---|---|
| `ProductName` | Name of the product |
| `Category` | Product category |

#### `Dim_Customers` *(Dimension)*

| Column | Description |
|---|---|
| `CustomerName` | Full customer name |
| `Country` | Customer country |
| `Region` | Regional grouping |
| `City` | Customer city |

#### `Dim_Date` *(Date Dimension)*

| Column | Description |
|---|---|
| `Month` | Month of transaction |
| *(standard date hierarchy)* | Enables time intelligence |

> Relationships are managed through Power BI's relationship editor with standard **many-to-one** joins from the fact table to each dimension.

---

## 📐 Key Metrics & DAX Measures

The following measures were created using **DAX (Data Analysis Expressions)**:

```dax
-- Total Revenue
Total Revenue = SUM(Facts_Table[SalesAmount])

-- Total Profit
Total Profit = SUM(Facts_Table[Profit])

-- Profit Margin %
% Profit Margin = DIVIDE([Total Profit], [Total Revenue], 0)

-- USD Total Sales
USD_Total Sales = SUMX(Facts_Table, Facts_Table[SalesAmount] * [Exchange Rate])
```

> These measures power the KPI cards and are reused across all four report pages, ensuring consistent, single-source-of-truth calculations.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Report authoring, data modeling, DAX |
| **Power BI Service** | Publishing, sharing, and web embedding |
| **DAX** | Calculated measures and KPIs |
| **Esri ArcGIS** | Geographic mapping visual |
| **Star Schema Modeling** | Optimized data model structure |
| **Power Query (M)** | Data transformation and loading |

---

## 🌐 How to Embed in a Website

Once the report is published to **Power BI Service**, follow these steps to embed it on any web page:

### Step 1 — Publish the Report to Power BI Service

1. In **Power BI Desktop**, click **Home → Publish**
2. Select your target **Workspace** (e.g., "My Workspace" or a team workspace)
3. Wait for the confirmation: *"Publishing to Power BI... Success!"*
4. Click **"Open [report name] in Power BI"** to verify it opens in your browser

---

### Step 2 — Generate a Public Embed Link

1. Open the report in **Power BI Service** (`app.powerbi.com`)
2. Click **File → Embed report → Publish to web (public)**

   > ⚠️ **Note:** This option makes the report publicly accessible to anyone with the link. Do not use this for sensitive/confidential data.

3. In the dialog that appears, click **"Create embed code"**
4. Accept the terms and click **Publish**
5. Power BI will generate:
   - A **shareable link** (for direct access)
   - An **HTML iframe snippet** (for embedding in websites)

---

### Step 3 — Copy the iframe Embed Code

The embed code will look like this:

```html
<iframe 
  title="PowerBI_Project" 
  width="1140" 
  height="541.25" 
  src="https://app.powerbi.com/reportEmbed?reportId=YOUR_REPORT_ID&autoAuth=true&ctid=YOUR_TENANT_ID" 
  frameborder="0" 
  allowFullScreen="true">
</iframe>
```

---

### Step 4 — Embed in Your Website or Portfolio

Paste the `<iframe>` code into your HTML file or CMS (e.g., GitHub Pages, WordPress, Notion, personal site):

```html
<!-- In your HTML page -->
<div class="dashboard-container">
  <h2>Sales Dashboard</h2>
  <iframe 
    title="PowerBI_Project" 
    width="100%" 
    height="600" 
    src="https://app.powerbi.com/reportEmbed?reportId=YOUR_REPORT_ID&autoAuth=true&ctid=YOUR_TENANT_ID" 
    frameborder="0" 
    allowFullScreen="true">
  </iframe>
</div>
```

> 💡 **Tip:** Set `width="100%"` and a fixed height for responsive layouts. You can also wrap it in a container with `overflow: hidden` for cleaner embedding.

---

### Step 5 — Verify & Share

1. Open the page where you embedded the iframe
2. Confirm the report loads and all interactive features (slicers, cross-filtering) work
3. Share the page URL — viewers can interact with the full report without needing a Power BI account

---

## ▶️ How to Run Locally

To explore or modify this report in Power BI Desktop:

1. **Download and install** [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. **Clone or download** this repository
3. Open `PowerBI_Project.pbix` in Power BI Desktop
4. If prompted about data source credentials, configure them under **Home → Transform data → Data source settings**
5. Click **Refresh** to reload the data

---

## ✅ Skills Demonstrated

This project showcases the following data analytics and BI competencies:

- ✅ **Data Modeling** — Star schema design with fact and dimension tables
- ✅ **DAX** — Custom measures for KPIs (revenue, profit, margin)
- ✅ **Power Query** — Data transformation and loading pipeline
- ✅ **Dashboard Design** — UX-conscious layout with KPI cards, charts, and slicers
- ✅ **Geographic Visualization** — ArcGIS map integration for regional analysis
- ✅ **Cross-filtering & Interactivity** — Connected visual interactions across the report
- ✅ **Publishing & Deployment** — Power BI Service publishing and public web embedding
- ✅ **Business Storytelling** — Structured pages that tell a coherent analytical narrative

---

## 📁 Repository Structure

```
📂 PowerBI-Sales-Dashboard/
├── 📄 PowerBI_Project.pbix     # Main Power BI report file
└── 📄 README.md                # This file
```

---

## 👤 Author

**[Your Name]**  
📧 [your.email@example.com]  
🔗 [LinkedIn Profile](#) | [Portfolio Website](#)

---

*Built with Power BI Desktop · Published via Power BI Service · © 2026*
