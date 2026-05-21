# HR Analytics Interactive Power BI Dashboard

## Executive Summary
This repository features a production-ready, interactive **HR Analytics Dashboard** built using Power BI. The project is specifically engineered to translate raw human resource transactions into strategic workforce insights. It provides organizational leadership and HR stakeholders with dynamic views to track headcount health, analyze demographic diversity, pinpoint attrition drivers, and implement data-backed retention strategies.

---

## 📊 Dashboard Architecture & Key Views

The report is divided into highly focused analytical views, each addressing a critical pillar of workforce planning:

### 1. Main Overview Panel
Designed for executive leadership to monitor core high-level metrics at a glance:
* **Key Performance Indicators (KPIs):** Instant visibility into **Total Employees**, **Active Employees**, and **Inactive Employees**.
* **Workforce Status Mapping:** A structured breakdown distinguishing between full-time staff and inactive records.
* **Departmental Dynamics:** Visual distributions tracking how headcount is allocated across core business functions.

### 2. Employee Demographics Deep-Dive
Focuses on understanding the composition, diversity, and equity profiles of the workforce:
* **Gender Representation:** Clear visual metrics tracking the balance of Male and Female employees across the organization.
* **Age Group Segmentation:** Distribution of the workforce into generational brackets to assist in succession planning and benefit tailoring.
* **Marital Status & Diversity Metrics:** Insights into the demographic background of the talent pool to foster an inclusive workplace culture.

### 3. Attrition & Retention Analytics
An investigative view dedicated to identifying why talent leaves and where the highest turnover risks reside:
* **Turnover Trends:** Longitudinal tracking of inactive employees to identify seasonal or annual attrition patterns.
* **Attrition by Demographics:** Cross-referencing departure rates against age groups, marital status, and gender to uncover underlying systemic patterns.
* **Departmental Attrition Heatmaps:** Pinpointing specific business units or job roles experiencing higher-than-average churn rates to optimize management practices.

---

## 🛠️ Technical Stack & Implementation Details

* **Business Intelligence Tool:** Microsoft Power BI Desktop
* **Data Engineering & Modeling:** Cleaned and transformed via Power Query, structured using an optimized **Star Schema** layout to maximize query speeds and report responsiveness.
* **Analytical Calculations (DAX):** Leverages advanced Data Analysis Expressions for dynamic time-intelligence tracking, active headcount filtering, and multi-conditional attrition rate slicing.

---

## 🚀 Getting Started & Setup

### Prerequisites
* Microsoft Power BI Desktop (Latest version recommended).

### How to Run and Refresh the Dashboard
1. Clone or download this repository to your local machine.
2. Open the `HR_Report.pbix` file using Power BI Desktop.
3. **To connect your own data:** * Navigate to the **Home** tab $\rightarrow$ **Transform Data** $\rightarrow$ **Data Source Settings**.
   * Update the source pathways to point to your organization's local CSV, Excel, or SQL Server HR tables.
   * Click **Refresh** on the home ribbon to re-populate the charts with your custom workforce data.

---
*Engineered to drive data-informed talent strategy, optimize operational efficiency, and mitigate workforce attrition.*
