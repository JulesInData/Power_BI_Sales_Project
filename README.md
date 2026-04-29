# Power_BI_Sales_Project
## 📊 Sales & Business Intelligence Dashboard — Power BI Project

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

![DAX](https://img.shields.io/badge/DAX-Measures-blue?style=for-the-badge)

![Data Model](https://img.shields.io/badge/Data%20Model-Star%20Schema-green?style=for-the-badge)

![Status](https://img.shields.io/badge/Status-Live%20%7C%20Web%20Embedded-brightgreen?style=for-the-badge)

A multi-page interactive Power BI dashboard built to analyze sales performance, regional distribution, product trends, and customer insights — with full web embed capability via Power BI Service.

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

## 🔗 Live Demo

🌐 This report has been published and embedded on the web via **Power BI Service**.  
 You can view the live, interactive version here: **[→ View Embedded Report](#)** *(replace with your embed link)*

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

**All visuals are cross-filtered** — clicking any data point dynamically updates all other visuals on the page.

<img width="1584" height="827" alt="image" src="https://github.com/user-attachments/assets/8329a510-45e3-40c6-9f55-58e65c733d1f" />

---

### 2. 🗺️ Regional Analysis

An interactive map-driven page that allows geographic drill-down into sales performance.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 🗺️ Esri ArcGIS Map | **Sales by Country & Region** — Plotted by Total Revenue |
| 🎛️ Slicer | Filter by **City** |

Uses **Esri ArcGIS Maps** integration within Power BI for rich geographic visualization. Revenue values are mapped as bubble sizes across countries and regions.

<img width="1599" height="808" alt="image" src="https://github.com/user-attachments/assets/fe16bc38-5f38-4488-9c71-f2aa5501622b" />

---

### 3. 📦 Product Analysis

A dedicated page for deep-diving into product-level performance.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 🌳 Treemap | **Sales by Product Name** — USD Total Sales weighted by area |
| 🎛️ Slicer | Filter by **Product Category** |

The treemap makes it immediately clear which products drive the most revenue through visual weighting.

<img width="1522" height="809" alt="image" src="https://github.com/user-attachments/assets/800463c2-1926-40b4-8c03-15defac1ad01" />

---

### 4. 👥 Customer Insights

Customer-level analysis that connects revenue contribution to profitability.

**Visuals included:**

| Visual Type | Description |
|---|---|
| 📊 Combo Chart (Line + Column) | **Revenue & Profit Margin by Customer** — dual-axis combo chart |
| 🎛️ Slicer | Filter by **Customer Name** |

 This combo chart overlays **Total Revenue** (columns) with **Profit Margin** (line) per customer — allowing easy identification of high-revenue but low-margin customers.
 
<img width="1582" height="818" alt="image" src="https://github.com/user-attachments/assets/87fa0ce8-6eac-4e07-98ba-505aac1c2038" />

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
<img width="1515" height="801" alt="image" src="https://github.com/user-attachments/assets/1420eeec-c4f0-4325-bc19-6d45d2d91838" />

### Tables & Key Columns

#### `Facts_Table` *(Fact Table)*
Central table containing all transactional sales data.

Columns and their Description 
| `Total Revenue` | Calculated revenue measure | 
<img width="746" height="36" alt="image" src="https://github.com/user-attachments/assets/be0ba4f3-5fac-458f-9bae-6cff971f5d81" />
| `ProfitMargin` | Margin as a ratio |
<img width="857" height="35" alt="image" src="https://github.com/user-attachments/assets/6a82e495-b63a-4734-aa5d-73c5ef3501d2" />
| `USD_Total Sales` | Revenue normalized to USD |
<img width="1098" height="33" alt="image" src="https://github.com/user-attachments/assets/6d79746b-3b14-4611-ab9d-d1da6329a403" />
| `Profit` | Profit per transaction |

| `SalesAmount` | Raw sales amount |

Here is the facts_table

<img width="1549" height="829" alt="image" src="https://github.com/user-attachments/assets/5806e811-cb23-4044-a724-cc4a1cc9e2fb" />

#### `Dim_Products` *(Dimension)*

| Column | Description |
|---|---|
| `ProductName` | Name of the product |
| `Category` | Product category |

<img width="1515" height="829" alt="image" src="https://github.com/user-attachments/assets/5f838585-4486-41d5-b486-89384245efa8" />

#### `Dim_Customers` *(Dimension)*

| Column | Description |
|---|---|
| `CustomerName` | Full customer name |
| `Country` | Customer country |
| `Region` | Regional grouping |
| `City` | Customer city |

<img width="1533" height="830" alt="image" src="https://github.com/user-attachments/assets/89ddd39e-237a-48f6-aa7b-3284f08251a6" />

#### `Dim_Date` *(Date Dimension)*

| Column | Description |
|---|---|
| `Month` | Month of transaction |
| *(standard date hierarchy)* | Enables time intelligence |

<img width="1520" height="830" alt="image" src="https://github.com/user-attachments/assets/dc0dc4a8-c1c8-41c0-b288-a761d681d16c" />

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

 These measures power the KPI cards and are reused across all four report pages, ensuring consistent, single-source-of-truth calculations.

---

## 🌐 How to Embed in a Website

Once the report is published to **Power BI Service**, follow these steps to embed it on any web page:

### Step 1 — Publish the Report to Power BI Service

1. In **Power BI Desktop**, click **Home → Publish**
   <img width="1319" height="192" alt="image" src="https://github.com/user-attachments/assets/4786bcdc-03db-4cd9-8603-1e1d19f7fe3a" />

2. Select your target **Workspace** (e.g., "My Workspace" or a team workspace)
   <img width="1590" height="717" alt="image" src="https://github.com/user-attachments/assets/94841571-cbf2-4c6a-8ce7-d219aee57248" />

3. Wait for the confirmation: *"Publishing to Power BI... Success!"*
   <img width="1583" height="711" alt="image" src="https://github.com/user-attachments/assets/8de716c9-f260-45ec-bd41-1f71cd6b4534" />

4. Click **"Open [report name] in Power BI"** to verify it opens in your browser
   <img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/18a59262-5770-4da9-87d8-4242c113a83c" />


---

### Step 2 — Generate a Public Embed Link

1. Open the report in **Power BI Service** (`app.powerbi.com`)
   
3. Click **File → Embed report → Publish to web (public)**
   <img width="1600" height="821" alt="image" src="https://github.com/user-attachments/assets/a16a46c5-66d3-4da5-a221-1b60df38d64c" />

    ⚠️ **Note:** This option makes the report publicly accessible to anyone with the link. Do not use this for sensitive/confidential data.

4. In the dialog that appears, click copy paste the html link
 <img width="1155" height="672" alt="image" src="https://github.com/user-attachments/assets/fa844c5f-a109-4558-83a0-2545b2b1c943" />

5. Accept the terms and click **Publish**
   
7. Power BI will generate:
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
