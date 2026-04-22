<div align="center">

# 📊 HR Analytics — Diversity & Inclusion KPI Dashboard

### Power BI · FY2020–2021 · 500 Employees · 6 KPI Modules

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://microsoft.com/excel)
[![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](./LICENSE)

<br/>

> **"Women rate 2.42. Men rate 2.41. Yet men receive 70% of all promotions."**
> 
> *This dashboard turns that contradiction into a business case for change.*

<br/>

</div>

---

## 🧭 Table of Contents

- [Project Overview](#-project-overview)
- [Dashboard Pages](#-dashboard-pages)
- [6 KPI Modules](#-6-kpi-modules)
- [Key Findings](#-key-findings)
- [Tools & Tech Stack](#%EF%B8%8F-tools--tech-stack)
- [File Structure](#-file-structure)
- [How to Use](#-how-to-use)
- [Strategic Recommendations](#-strategic-recommendations)
- [Business Value](#-business-value)
- [Author](#-author)

---

## 🎯 Project Overview

This project delivers a **3-page interactive Power BI dashboard** that gives HR leadership and C-Suite executives real-time visibility into gender diversity and inclusion metrics across a 500-employee organisation.

Built on FY2020–FY2021 HR data, the dashboard tracks **6 critical KPIs** with dynamic filtering by Age Group, Region, Job Level, and Department — enabling targeted, data-driven decisions rather than broad assumptions.

### The Core Business Question
> *Do we have a talent problem — or a fairness problem?*

The data answers it definitively: **it's a fairness problem.** Women and men perform identically. The disparity exists in hiring pipelines, promotion decisions, and executive appointment — not in capability.

---

## 📺 Dashboard Pages

### Page 1 · HR Diversity Overview
![HR Diversity Dashboard](./HR%20Diversity%20Dashborad.png)

*Top-line headcount metrics · Promotion trends FY20/FY21 · Nationality distribution · Job diversity pyramid · Regional breakdown · Employee turnover · Age diversity*

---

### Page 2 · KPI Details: Hiring · Promotions · Turnover
![KPIs Page 1](./KPIs%201.png)

*KPI 1: Gender split of hires by job level · KPI 2: Promotion counts + avg time-in-grade by gender · KPI 3: FY20 leaver turnover rate by job level*

---

### Page 3 · KPI Details: Performance · Executive Balance · Age Groups
![KPIs Page 2](./KPIs%202.png)

*KPI 4: Performance ratings by gender · KPI 5: Executive gender split FY20 → FY21 · KPI 6: Age group distribution by job level post-FY21 promotions*

---

## 📐 6 KPI Modules

| # | KPI | Chart Type | Key Metric |
|---|-----|-----------|------------|
| 1 | **Hiring** | Stacked Bar + Clustered Bar | 41% Female vs 59% Male overall hires |
| 2 | **Promotions** | Clustered Bar + Horizontal Bar | 29.9% Female vs 70.1% Male total promotions |
| 3 | **Turnover Rate** | Dual Line Chart | 9.4% employee turnover (47 FY20 leavers) |
| 4 | **Performance Rating** | Stacked Bar + KPI Cards | Women 2.42 avg vs Men 2.41 avg (near-identical) |
| 5 | **Executive Gender Balance** | 4× Donut Charts | 12.5% female executives · 0% female exec appointments in FY20 |
| 6 | **Age Group Distribution** | Bar + Stacked Bar | 75% of workforce under 40 · 215 employees aged 20–29 |

---

## 🔍 Key Findings

### 🚨 Critical Discovery: The Fairness Gap

```
Performance Rating:   Women = 2.42   ·   Men = 2.41   ← EQUAL
Total Promotions:     Women = 29.9%  ·   Men = 70.1%  ← NOT EQUAL
Executive Level:      Women = 12.5%  ·   Men = 87.5%  ← SEVERELY UNEQUAL
Exec Appointments:    Women = 0%     ·   Men = 100%   ← FY20 + FY21 combined
```

**The verdict:** Equal performance + unequal advancement = structural inequity.

### 📊 Dashboard Highlights

- **500 employees** · 295 Male (59%) · 205 Female (41%)
- **47 FY20 leavers** — mid-to-high performers, not low performers
- **9.4% turnover rate** — moderate, but costly if D&I-related
- **215 employees aged 20–29** — largest single cohort; the future of the org
- **Switzerland-dominant** workforce (250+) with European diversity across 15+ countries
- At Executive level: only **13% of hires are female**
- At Junior Officer: **53% of hires are female** — pipeline exists at base, breaks higher up
- Female promotees wait **longer in grade** at senior levels before advancing

---

## 🛠️ Tools & Tech Stack

| Tool | Purpose |
|------|---------|
| **Microsoft Power BI Desktop** | Data modelling, DAX measures, interactive visualisations, slicers |
| **Microsoft Excel** | Source data storage, data preparation, initial analysis |
| **DAX (Data Analysis Expressions)** | Custom KPI measures, % calculations, time-intelligence |
| **Power Query (M Language)** | Data transformation and cleaning |

### DAX Measures Used
```dax
-- % Female Hires
% Female Hires = 
DIVIDE(
    CALCULATE(COUNTROWS(HR_Data), HR_Data[Gender] = "Female"),
    COUNTROWS(HR_Data),
    0
)

-- Avg Performance Rating by Gender
Avg Perf Rating = AVERAGE(HR_Data[FY20 Performance Rating])

-- Turnover Rate
Turnover Rate = 
DIVIDE(
    CALCULATE(COUNTROWS(HR_Data), HR_Data[FY20 leaver?] = "Yes"),
    COUNTROWS(HR_Data),
    0
)

-- % Female Promoters
% Female Promoters = 
DIVIDE(
    CALCULATE(COUNTROWS(HR_Data), HR_Data[Gender] = "Female", HR_Data[Promotion in FY21?] = "Yes"),
    CALCULATE(COUNTROWS(HR_Data), HR_Data[Promotion in FY21?] = "Yes"),
    0
)
```

---

## 📁 File Structure

```
hr-analytics-diversity-inclusion-powerbi/
│
├── 📊  HR Diversity Inclusion Dashboard.pbix   ← Main Power BI file
├── 🖼️  HR Diversity Dashborad.png              ← Overview page screenshot
├── 🖼️  KPIs 1.png                              ← KPI page 1 screenshot (KPIs 1–3)
├── 🖼️  KPIs 2.png                              ← KPI page 2 screenshot (KPIs 4–6)
├── 📄  README.md                               ← This file
└── 📜  LICENSE                                 ← MIT License
```

---

## 🚀 How to Use

### Prerequisites
- Microsoft Power BI Desktop (free download: [powerbi.microsoft.com](https://powerbi.microsoft.com/desktop))
- Windows OS (Power BI Desktop is Windows-only)

### Steps

1. **Clone or download** this repository
   ```bash
   git clone https://github.com/YOUR-USERNAME/hr-analytics-diversity-inclusion-powerbi.git
   ```

2. **Open** `HR Diversity Inclusion Dashboard.pbix` in Power BI Desktop

3. **Explore** the 3 dashboard pages using the page tabs at the bottom

4. **Use the 4 slicers** to filter the entire dashboard dynamically:
   - `Age Group` — Filter by age band (16-19, 20-29, 30-39, 40-49, 50+)
   - `Region Group` — Filter by geographic region
   - `Job Level` — Filter by seniority (Executive → Junior Officer)
   - `Department` — Filter by business department

5. **Refresh with new data** — Replace the source Excel file and click Refresh All

### Power Tip: Most Revealing Filter Combinations
| Filter | What It Reveals |
|--------|----------------|
| Job Level = Executive | Starkest gender imbalance in the entire report |
| Age Group = 20 to 29 | The future talent pipeline — is it being developed fairly? |
| Region = Switzerland | Whether the home market mirrors or diverges from global patterns |

---

## 💡 Strategic Recommendations

Based on the dashboard findings, here are the 6 prioritised actions:

| Priority | Action | Target |
|----------|--------|--------|
| 🔴 Critical | Set mandatory 30% female executive target by 2027 | Exec appointments |
| 🔴 Critical | Structured promotion calibration with gender panel review | 45% female promotions in 18 months |
| 🟡 High | Senior hiring: partner with women's executive search networks | 25% female Exec hires in 2 years |
| 🟡 High | Mandatory exit interview data capture by gender + level | Understand who is leaving and why |
| 🟢 Medium | Mentorship + career development for 20–29 cohort | Protect the future pipeline |
| 🟢 Medium | Quarterly D&I KPI reporting to all managers | Accountability at every level |

---

## 💼 Business Value

### Why This Dashboard Matters

1. **Uncovers the root cause** — Not "we need more female talent" but "we're not advancing the talent we have"
2. **Quantifies the cost of inaction** — 47 leavers × €80–120K replacement cost = €3.7–5.6M annual exposure
3. **Creates accountability** — Real-time KPIs make it impossible to claim ignorance
4. **Supports compliance** — EU CSRD, Gender Pay Gap reporting, ESG disclosures all increasingly require this data
5. **Enables targeted action** — The 4 slicers mean interventions can be scoped by level, region, age, and department

### Applicability Beyond This Dataset

| Industry | Application |
|----------|------------|
| Financial Services | Regulatory gender reporting (EU, UK FCA) |
| Technology | Engineering pipeline diversity tracking |
| Healthcare | Physician leadership gender balance |
| Retail | Store management diversity at scale |
| Manufacturing | Factory floor + management diversity split |

---

## 👤 Author

**[Your Name]**  
Data Analyst | Power BI · Excel · SQL · Python

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/kiransindam/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat-square&logo=github)](https://github.com/kiransindam)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-orange?style=flat-square)](https://aistudio.google.com/apps/80abc1d3-fe16-48f2-a577-f20e4c746d99?fullscreenApplet=true&showPreview=true&showAssistant=true)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

Data is used for educational and portfolio demonstration purposes.

---

<div align="center">

**If this project helped you, please ⭐ star the repository!**

*Built with Power BI · Powered by data · Driven by fairness*

</div>
