# Dipjyoti Karmakar
### Data Analyst · Business Analyst · BI Developer

📍 Assam, India  |  ✉️ dipjyotikarmakar97@gmail.com  |  [LinkedIn](https://www.linkedin.com/in/dipjyoti-karmakar-dk/)  |  [GitHub](https://github.com/Dipjyoti-Karmakar)

---

> 💡 **About Me**
>
> Ranked **#1 Top Performer** in the Data Analytics with GenAI batch at Career247. I build end-to-end analytics solutions: from normalized SQL schemas and Python pipelines to live web apps powered by the Gemini and GitHub APIs. My projects cover $11.96B+ in modeled revenue across six domains, and every finding I deliver connects directly to a business decision someone has to make.
>
> Currently pursuing an MBA at Bodoland University while working in Python, SQL, and Power BI.

---

## 📊 By the Numbers

| Metric | Value |
|---|---|
| Largest dataset analyzed | 550,068 transactions |
| Total revenue modeled across projects | $11.96B+ |
| Batch ranking - Career247 Data Analytics with GenAI | **#1 Top Performer** |
| Repeat customers identified (coffee analytics) | 545 |
| Flux app commits shipped | 56 |
| Single-file web apps built | 2 (Flux · Dossier.ai) |
| Chart.js visualizations in Dossier.ai | 5 live charts |
| SQL records managed (retail DB) | 400 orders · 50 products · 30 customers |
| Stock units under automated inventory alert | 5,102 units across 5 categories |

---

## 🛠️ Skills Matrix

### 🗄️ Data Architecture & Pipelines
`Python` · `Pandas` · `NumPy` · `SciPy` · `MySQL` · `PostgreSQL` · `SQL Server` · `PyMySQL` · `ETL` · `DDL/DML` · `Joins` · `CTEs` · `Subqueries` · `Feature Engineering` · `Data Cleaning` · `Data Validation`

### 📊 Visualization & BI
`Power BI` · `DAX` · `Power Query` · `Tableau` · `Matplotlib` · `Seaborn` · `Canvas 2D API` · `KPI Dashboards` · `Trend Analysis` · `Ad-hoc Reporting`

### 📐 Statistical & Analytical Methods
`EDA` · `Hypothesis Testing` · `Welch's T-Test` · `One-Way ANOVA` · `Statistical Modeling` · `Customer Segmentation` · `CLV Engineering` · `Risk Classification` · `R` · `scikit-learn`

### ⚙️ Cloud, Web & Integration
`Firebase Auth` · `Cloud Firestore` · `IndexedDB` · `Service Workers` · `PWA` · `HTML5` · `CSS3` · `Vanilla JavaScript (ES2020)` · `SheetJS` · `Google Gemini API` · `GitHub REST API` · `Chart.js` · `html2canvas` · `Git` · `GenAI for Analytics`

### 📋 Business & Productivity Tools
`Microsoft Excel` · `VLOOKUP` · `INDEX-MATCH` · `Pivot Tables` · `Power Pivot`

---

## 🏆 Certifications & Achievements

🥇 **#1 Top Performer · Career247 · March 2026** - [View Proof](https://drive.google.com/file/d/11_z6inyomCbX-C26laU1CM3oadTsY9wP/view?usp=sharing)

📜 **Data Analytics with GenAI · Career247 · March 2026** - [View Certificate](https://drive.google.com/file/d/1ocjO1p7GAp4SfaA71yxUf5U7x8s1UNWO/view?usp=sharing)

---

## 🚀 Project Gallery

---

### 01 · Black Friday Sales Analysis

> 🛒 **550,068 transactions. $5B+ in revenue. The question was: which customer segments actually drive spending, and is there statistical proof?**
>
> Every finding in this project is backed by formal hypothesis testing. The output is a reproducible Python pipeline, a MySQL-backed dataset, and a multi-page Power BI dashboard ready for stakeholder review.

**Stack:** `Python` · `Pandas` · `NumPy` · `SciPy` · `MySQL` · `Power BI` · `Excel` · `Jupyter`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/black-friday-sales-analysis)

**Situation**
A retailer had 550,068 Black Friday transactions worth over $5 billion but no clear understanding of which demographic or geographic factors were driving purchases. Without that, marketing spend had no data to guide it.

**Task**
Build a complete analytics pipeline from raw CSV to final dashboard, covering data ingestion, feature engineering, statistical validation, and a Power BI report for both executive and marketing audiences.

**Action**
Built a modular `src/` pipeline with transformation logic kept separate from the analysis notebooks, so the processed dataset can be rebuilt with a single command. Computed two custom features: Customer Lifetime Value (CLV) and Category Breadth using Pandas and NumPy. Applied Welch's T-Test to test gender-based spending differences and One-Way ANOVA to check whether city category and age group significantly affect revenue. Loaded the results into MySQL and built a multi-page Power BI dashboard with separate views for executive and marketing teams.

**Result**
The analysis identified a clear Power Consumer profile (Male, age 26-35, City B, 1-2 year resident) and proved that marital status has no statistically significant effect on spending. That second finding has a direct budget implication: any targeting spend against marital status was wasted, and can be reallocated. The pipeline is fully reusable: one command rebuilds the entire processed dataset from raw CSV.

**Pipeline Architecture**
```
Raw CSV (data/raw/)
      ↓
Feature Engineering + Cleaning (src/data_processing.py)
      ↓
Processed Master Dataset (data/processed/)
      ↓
Statistical Testing - SciPy (Welch's T-Test · One-Way ANOVA)
      ↓
Multi-page Power BI KPI Dashboard (Executive + Marketing views)
```

**Proof of Work - Python: CLV & Category Breadth**
```python
# Customer Lifetime Value - total spend per customer
clv = df.groupby('User_ID')['Purchase'].sum().reset_index()
clv.columns = ['User_ID', 'CLV']

# Category Breadth - unique product categories per customer
category_breadth = df.groupby('User_ID')['Product_Category_1'].nunique().reset_index()
category_breadth.columns = ['User_ID', 'Category_Breadth']

# Merge back into master dataset
df = df.merge(clv, on='User_ID', how='left')
df = df.merge(category_breadth, on='User_ID', how='left')
```

**Key Findings**
- 🎯 Male, 26-35, City B = highest individual revenue segment
- 🏙️ City B leads total sales volume across all city categories
- 🚫 Marital status: statistically insignificant - remove from targeting models, reallocate that budget
- 📈 Residents of 1-2 years show the highest per-transaction spend

---

### 02 · Retail Sales & Customer Analytics Database System

> 🗃️ **$6.96M in revenue, 400 orders, and no database. Every question about top customers or stock levels required manual spreadsheet work. This project fixed that.**
>
> The goal was to build a normalized relational database, write queries that answer real business questions, and output clean datasets that feed directly into BI tools.

**Stack:** `SQL` · `MySQL` · `PostgreSQL` · `Relational Schema Design` · `CTEs` · `Subqueries`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/retail-sales-sql-analytics)

**Situation**
A retail operation with $6.96M in order revenue across 400 orders had no structured database. Basic questions about top customers, stock levels, or product performance required manual spreadsheet work each time.

**Task**
Design a normalized relational schema with data integrity constraints, populate it with transactional data, and write SQL queries that answer revenue, customer, and inventory questions with output clean enough for Power BI.

**Action**
Built a 3-table normalized schema (`Customers`, `Products`, `Sales`) with primary and foreign key relationships and `NOT NULL` / `CHECK` constraints to reject bad data at entry. Wrote analytical queries using `INNER`, `LEFT`, and `RIGHT` joins, `GROUP BY` aggregations, CTEs, and subqueries. Set up automated low-stock alerts across 5 product categories covering 5,102 total stock units.

**Result**
Top customers by spend, monthly revenue trends, order status, and best-performing categories can now be answered in seconds instead of hours of manual work. Average order value came in at $17,402. The schema connects directly to Power BI without any additional transformation, making it a ready feed for executive dashboards.

**Proof of Work - SQL: Top Customers + Inventory Alert**
```sql
-- Top 5 customers by total spend
WITH CustomerRevenue AS (
    SELECT
        c.Customer_ID,
        c.Customer_Name,
        SUM(s.Total_Amount)  AS Total_Spend,
        COUNT(s.Order_ID)    AS Total_Orders
    FROM Customers c
    INNER JOIN Sales s ON c.Customer_ID = s.Customer_ID
    GROUP BY c.Customer_ID, c.Customer_Name
)
SELECT *
FROM CustomerRevenue
ORDER BY Total_Spend DESC
LIMIT 5;

-- Products below reorder threshold
SELECT
    Product_ID,
    Product_Name,
    Category,
    Stock_Level,
    Unit_Price
FROM Products
WHERE Stock_Level < 50
ORDER BY Stock_Level ASC;
```

**Key Findings**
- 💰 Total order revenue: $6,960,973 · Average order value: $17,402
- 📦 5 product categories monitored across 5,102 stock units
- 👥 Customer revenue ranking available on demand, no manual aggregation needed
- 📅 Monthly revenue queryable in real time for seasonal planning

---

### 03 · Flux - Personal Finance Web App

> 💸 **Most personal finance apps require a backend, a framework, and a build process. Flux has none of those.**
>
> It is a cloud-synced finance dashboard that ships as a single HTML file. Real-time sync, offline storage, and multi-view analytics. 56 commits. One file.

**Stack:** `HTML5` · `CSS3` · `Vanilla JavaScript (ES2020)` · `Firebase Auth` · `Cloud Firestore` · `SheetJS` · `PWA` · `Service Worker`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/flux-personal-finance-dashboard) · 🌐 [Live Demo](https://dipjyoti-karmakar.github.io/flux-personal-finance-dashboard)

**Situation**
Most personal finance tools are either too basic to be useful or require too much setup to be practical. The goal was a tracker that works across devices, has real analytics built in, and works offline.

**Task**
Build a complete, installable web app with no frameworks, no build tools, and no backend. It needed to handle real-time transaction tracking, financial analytics, cloud sync, and offline use, all from a single HTML file.

**Action**
Built a ~3,100-line single-file app (`index.html`) using CSS custom properties and ES2020 modules. Connected Firebase Auth for Google sign-in and Cloud Firestore with `onSnapshot` listeners and 120ms debounced rendering to handle batch import bursts. Wrote a custom Canvas 2D trend chart with no charting library, including crosshair hover, gradient fill, and ARIA screen-reader labels. Added SheetJS for Excel/CSV import with auto column mapping, row validation, duplicate detection, and 450-op batch writes. Included a Service Worker and IndexedDB persistence for offline use.

**Result**
The app is live, installable as a PWA, and works fully offline. It includes real-time sync across devices, Excel import and export, and a multi-view analytics dashboard covering net balance, category breakdown, monthly comparisons, and yearly overview with sparklines. Touch users get swipe-to-edit and swipe-to-delete. Undo on delete stays active for 5 seconds. Built across 56 commits.

**Firestore Data Model**
```
users/{uid}/
  transactions/{txId}
    ├── type      "income" | "expense"
    ├── mode      "online" | "offline"
    ├── cat       food | transport | salary | ...
    ├── amount    number > 0
    ├── date      "YYYY-MM-DD"
    └── eventId   (optional) linked special event

  events/{eventId}
    ├── name, start, end   (date range)
    └── color              (hex tag)
```

**Key Highlights**
- ⚡ Firestore sync with 120ms debounced rendering handles batch import bursts cleanly
- 📊 Custom Canvas 2D chart, no library, with crosshair hover, gradient fill, and ARIA labels
- 📥 Excel/CSV import: auto column mapping, duplicate detection, 450-op batch write
- 🔄 Full offline support via Service Worker + IndexedDB, syncs on reconnect
- 🎨 Dark/light theme toggle with circular clip-path wipe animation

---

### 04 · Social Media Addiction Analysis

> 📱 **Addiction scores in a dataset represent real patterns: poor sleep, declining grades, and interpersonal conflict. This project analyzes that data by demographic group, assigns risk tiers using a rule-based classifier, and produces a dashboard that a school or wellness program can use to prioritize who needs attention first.**

**Stack:** `Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Power BI` · `Jupyter`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/social-media-addiction-analysis)

**Situation**
Student wellness programs are often built on assumption rather than data. There was no demographic breakdown of which student groups are at highest risk or which patterns are most likely to predict poor academic outcomes.

**Task**
Analyze student social media behavior data to find patterns in addiction risk by gender, age, and academic level. Build a rule-based Python classifier to assign risk tiers and generate intervention suggestions. Present findings in a Power BI dashboard.

**Action**
Checked dataset for nulls, duplicates, and schema issues. Ran grouped EDA using Matplotlib and Seaborn covering addiction score distributions by gender, daily usage by age group, platform preferences, and sleep/conflict cross-analysis. Built rule-based Python logic to assign risk tiers and generate digital detox suggestions per student profile. Built a Jupyter report and a 5-view Power BI dashboard covering demographics, usage patterns, conflict analysis, platform comparison, and academic impact.

**Result**
The output gives program designers a ranked list of which groups to target first, based on data rather than assumption. High school students, ages 19-20, and female students came out as the highest-risk segments. Dashboard analysis confirmed that higher conflict rates align directly with lower sleep and weaker academic performance, giving intervention teams a clear signal of where to focus limited resources.

**Key Findings**
- 👩‍🎓 High school students = highest addiction score across all academic levels
- 😴 Higher conflict rates correlate with lower sleep and weaker academic performance
- 🎯 Ages 19-20 show the highest concentration of heavy daily usage
- 📋 Rule-based classifier assigns risk tiers without needing a trained ML model

---

### 05 · Coffee Retail Sales & Customer Analytics

> ☕ **Knowing Latte is your top product is a starting point. Knowing it peaks at 18:00, that 95.66% of customers pay by card, and that 545 are repeat buyers - that is the basis for a staffing decision, an infrastructure investment, and a loyalty program.**

**Stack:** `Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Jupyter`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/coffee-sales-business-analytics)

**Situation**
A coffee retail operation had transaction data across products, time periods, and payment modes but no analysis to guide inventory decisions, staffing, or loyalty program planning.

**Task**
Merge and clean two source datasets, then analyze four areas: product revenue, peak transaction timing, payment behavior, and repeat customer identification.

**Action**
Merged 2 raw datasets into 3,898 clean transactions using Pandas. Ran product-level revenue ranking, hourly frequency analysis to find peak windows, payment mode breakdown, repeat customer identification by card usage, and cross-month trend analysis.

**Result**
Every finding here maps to an operational decision. Latte at $28,658 across 806 purchases tells you what to protect in your inventory. Peak hour at 18:00 with 113 transactions tells you when to schedule your best staff. 95.66% card usage makes the case for contactless payment infrastructure. And 545 identified repeat customers is a ready base for a loyalty program that doesn't need to be built from scratch.

**Key Findings**
- ☕ Latte: $28,658 revenue across 806 purchases - top priority for stock and upsell
- 🕕 Peak hour: 18:00 (113 transactions) - schedule staffing and restocking around this
- 💳 95.66% card payment rate supports the case for contactless infrastructure
- 🔄 545 repeat customers identified by card - ready base for a loyalty program

---

### 06 · Dossier.ai - GitHub Profile Intelligence Dashboard

> 🤖 **Paste any GitHub username and the app generates a full developer report: tech stack inference, career suggestions, a 90-day activity heatmap, and a side-by-side comparison with any other GitHub user.**
>
> Dossier.ai is a single HTML file with no backend, no server, and no build step. It runs on GitHub Pages and is publicly accessible.

**Stack:** `HTML5` · `CSS3` · `Vanilla JavaScript (ES2020)` · `Google Gemini API (gemini-1.5-flash)` · `GitHub REST API v3` · `Chart.js v4.4.0` · `html2canvas v1.4.1`

🔗 [View Repository](https://github.com/Dipjyoti-Karmakar/dossier.ai) · 🌐 [Live Demo](https://dipjyoti-karmakar.github.io/dossier.ai)

**Situation**
Looking at a GitHub profile usually means reading through a list of repos manually or relying on basic stats widgets that show numbers with no context. There was no simple tool that combined live profile data, AI analysis, and visual charts in one place.

**Task**
Build a client-side tool that pulls any public GitHub profile via the REST API, sends the data to Google Gemini for analysis, and shows the results as a multi-panel dashboard with live charts, a comparison tool, and PNG export. No backend code.

**Action**
Built a single `index.html` file connecting two external APIs: GitHub REST API v3 for profile data, repo metadata, and event history, and Google Gemini (gemini-1.5-flash) for AI summaries, stack inference, career suggestions, and code quality reviews. Added 5 Chart.js visualizations: a Skills Radar across 6 dimensions, a Language Breakdown Bar for 40+ languages, a Star/Fork Trend Line for the top 10 repos, a 90-Day Activity Heatmap (13-week grid), and a Live Activity Feed. Discover Mode takes a plain-English description of a tool need, sends it to Gemini to generate search terms, then queries the GitHub Search API for matching repos. Also built a Developer Compare mode for head-to-head stats across 6 metrics, Deep Repo Analysis modals with AI README summaries and code critique, PNG export via html2canvas at 2x resolution, and Web Share API support. API keys are stored in `localStorage` only and never sent through any intermediate server.

**Result**
The app is live at `https://dipjyoti-karmakar.github.io/dossier.ai` and works on any device without installation. Forked repos are excluded from all visualizations so the stats reflect original work only. The project covers API integration, Gemini prompt design, data visualization, and client-side privacy in a single deployable file.

**Feature Map**
| Feature | Technology | What it does |
|---|---|---|
| AI Profile Analysis | Gemini API | Developer summary, stack inference, career suggestions, profile audit, Code Personality archetype |
| Skills Radar | Chart.js | Scores across 6 dimensions from actual repo data |
| 90-Day Heatmap | Chart.js + GitHub Events API | Activity intensity grid based on last 300 public events |
| Discover Mode | Gemini + GitHub Search API | Plain-English input to precise repo recommendations |
| Developer Compare | GitHub REST API | Head-to-head across followers, repos, stars, forks, Dossier Score, streak |
| Deep Repo Analysis | Gemini + Chart.js | AI README summary, code critique, and engagement charts |
| PNG Export | html2canvas (2x scale) | High-res shareable profile card |
| Privacy | localStorage only | API keys stay in the browser, verifiable in the open-source code |

**Key Technical Points**
- 🤖 Gemini prompt design produces structured output: summaries, audits, code critiques, search terms
- 📊 5 Chart.js charts driven by live GitHub API data
- 🔍 Discover Mode: plain-English input to Gemini to GitHub Search API to ranked results
- 🔒 All API keys in `localStorage`, all calls go directly from browser to API
- 🚀 Deployed on GitHub Pages, no hosting cost, publicly accessible

---

## 🎓 Education

| Degree | Institution | Status |
|---|---|---|
| MBA, Business Administration | Bodoland University, Kokrajhar, Assam | Expected Aug 2027 |
| B.Com (CBCS) | Pandit Deendayal Upadhyaya Adarsha Mahavidyalaya, Assam | Completed Jun 2025 |

---

## 💼 Work Experience

### DatNex · Lead Generation Associate
*December 2025 – March 2026*

- Built and maintained B2B prospect lists for 500+ IT and SaaS companies using `Apollo.io`, `LinkedIn Sales Navigator`, and `Excel`. Cleaned and enriched contact data to ensure accuracy before outreach, segmenting decision-makers (CMOs, VP Demand Gen, Marketing Directors) by industry, region, and tech stack to match each client's ICP.
- Ran personalized outbound campaigns through `Outlook` and `Instantly.ai` with technographic references (RPA tools: UiPath, Automation Anywhere), tracking engagement and qualified meeting bookings to measure campaign effectiveness against pipeline targets.

---

## 🤝 Let's Connect

Looking for Data Analyst and Business Analyst roles. Open to full-time positions, internships, and project collaborations.

📩 dipjyotikarmakar97@gmail.com
🔗 [linkedin.com/in/dipjyoti-karmakar-dk](https://www.linkedin.com/in/dipjyoti-karmakar-dk/)
💻 [github.com/Dipjyoti-Karmakar](https://github.com/Dipjyoti-Karmakar)

---

## 🌐 Languages

English · Hindi · Bengali · Assamese

---

*Last updated: April 2026.*
