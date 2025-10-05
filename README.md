## Power BI Dashboard – Manufacturer Analysis

*(University Coursework Project – MSc Informatics, Czech University of Life Sciences)*

This Power BI project was developed as part of my Master’s coursework in Informatics to demonstrate a **complete Business Intelligence (BI) lifecycle** — starting from **data extraction, transformation, and modelling**, all the way to **dashboard visualization and storytelling**.

The project simulates a **manufacturer’s sales and revenue performance** across regions, years, and customer segments, highlighting how Power BI can turn raw data into actionable business insights.

---

## Project Objectives

The main objectives of this BI project were to:

1. Practice end-to-end Power BI report development — from raw data to insights.
2. Design an **interactive and visually engaging dashboard** that helps managers understand sales trends, growth, and segment performance.
3. Apply **data cleaning, modelling, and DAX calculations** to support analytical queries and comparisons between current and previous year sales.
4. Communicate findings through professional visuals and dashboards ready for publishing in the Power BI Service.

---

## Dataset Description

The dataset provided in the DIAD (Data Insights and Decision) lab consists of multiple files (Excel and CSV) that represent a simplified manufacturing company’s operations.

**Main tables:**

| Table            | Description                                                           |
| ---------------- | --------------------------------------------------------------------- |
| **Sales**        | Contains transactional data (revenue, quantity, date, and geography). |
| **Date**         | Calendar table for time intelligence (year, month, quarter).          |
| **Product**      | Details about product categories, segments, and MSRP.                 |
| **Geography**    | Information about regions, countries, and states.                     |
| **Manufacturer** | List of manufacturers (Fabrikam, VanArsdel, Tailwind Traders, etc.).  |

The data simulates real-world corporate performance and is ideal for practicing **data integration, relationships, and BI modelling**.

---

## Data Preparation & Modelling

Data preparation was performed using **Power Query**, applying transformations such as:

* Removing duplicates and null values.
* Standardizing field names and formats.
* Detecting and correcting data type inconsistencies.
* Creating custom columns for derived metrics (e.g., RegionGroup, CategoryLevel).
* Merging tables using keys (e.g., `ProductID`, `Date`, `Country`).

In **Model View**, relationships were created as follows:

* `Sales[ProductID] → Product[ProductID]`
* `Sales[Date] → Date[Date]`
* `Sales[GeographyID] → Geography[GeographyID]`
* `Product[ManufacturerID] → Manufacturer[ManufacturerID]`

This **star schema** design ensured optimal performance and supported **DAX time intelligence calculations**.

---

## Key DAX Measures

Several calculated measures were created to support the analysis, including:

```DAX
Revenue = SUM(Sales[Revenue])

PY Sales = CALCULATE(SUM(Sales[Revenue]), SAMEPERIODLASTYEAR(Date[Date]))

% Growth = DIVIDE([Revenue] - [PY Sales], [PY Sales])
```

These formulas allowed for **year-over-year growth comparisons**, performance tracking, and visual storytelling.

---

## Dashboard Design

The dashboard was structured into two key report pages:

### ** 1. Overview Page**

Focuses on the *global business performance*:

* **Total Revenue and Previous Year Sales:** Compared current and prior results using bar charts.
* **% Growth by Year:** A line chart showing annual revenue growth and decline trends.
* **Revenue by Country:** Clustered column chart visualizing top-performing countries.
* **Revenue by Segment:** Pie chart summarizing the contribution of each business segment (e.g., Extreme, Moderation, Convenience).

*Insights:*

* USA leads with the highest total revenue.
* “Extreme” and “Urban” segments contributed nearly 50% of total sales.
* Global growth slowed after 2020 due to market saturation.

---

### ** 2. Manufacturer Analysis Page**

Drills down into manufacturer-specific metrics:

* **Revenue by Country and State:** Column chart comparing performance across regions.
* **Segment Table with % Growth:** Detailed matrix combining revenue, growth rate, and year-on-year variance by segment.
* **Revenue & Growth by Year:** Combo chart showing total revenue (bars) and growth % (line).

*Insights:*

* VanArsdel Ltd. and Fabrikam Inc. were the top manufacturers in total revenue.
* Moderate and Convenience segments showed consistent growth (above 20%).
* Negative growth periods were identified post-2020, suggesting areas for efficiency improvements.

---

## 🎨 Design Elements

The dashboard includes advanced Power BI design features:

* **Custom theme** (colors, typography, and background).
* **Conditional formatting** for highlighting top and bottom performers.
* **Data labels** for clarity and visual precision.
* **Bookmarks & Buttons** to create a guided navigation experience.
* **Slicers & Filters** for interactivity (Year, Country, Segment).
* **Logos and branding** (VanArsdel Ltd., Tailwind Traders, etc.) for professional presentation.

---

## Business Insights Summary

| Area                       | Key Finding                                                                |
| -------------------------- | -------------------------------------------------------------------------- |
| **Top Revenue Region**     | USA – £266M total revenue (50.9% of total)                                 |
| **Fastest Growth Segment** | Urban Segment – 29.2% YoY Growth                                           |
| **Overall Trend**          | Revenue increased by 156% between 2014–2021, followed by a decline in 2022 |
| **Operational Insight**    | Power BI identified underperforming states and years for managerial review |

---

## Tools & Skills Applied

| Category                | Tools / Techniques                               |
| ----------------------- | ------------------------------------------------ |
| **Data Modelling**      | Power BI Desktop, Power Query, DAX               |
| **Data Cleaning**       | Excel, CSV integration, field transformations    |
| **Visualization**       | Bar, Line, Pie, Matrix, and Combo charts         |
| **Analysis Techniques** | KPI comparison, YoY growth, trend analysis       |
| **Business Skills**     | BI reporting, performance tracking, storytelling |

---

## Learning Outcomes

Through this project, I strengthened my skills in:

* Translating **business needs into analytical questions**.
* Applying **data modelling and DAX logic** to support decision-making.
* Communicating insights through **clear, dynamic, and interactive visuals**.
* Practicing **BI workflow management** — from data loading to final presentation.

---

## Author

**Diaa Abu Arar**
M.Sc. Informatics |

