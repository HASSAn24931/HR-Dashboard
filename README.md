# HR Analytics Power BI Dashboard

## Executive Summary
This repository contains a comprehensive **Human Resources (HR) Analytics Dashboard** built using Power BI. The project transforms raw human resource data into actionable strategic insights, enabling leadership, HR managers, and department heads to monitor workforce dynamics, optimize retention strategies, streamline recruitment, and foster diversity and inclusion across the organization.

By leveraging advanced data modeling, DAX (Data Analysis Expressions), and modern data visualization techniques, this dashboard provides a 360-degree view of organizational health and employee lifecycles.

---

## Key Features & Analytical Views

### 1. Workforce Overview (Demographics & Structure)
* **Headcount Tracking:** Real-time visibility into total active employees, contractors, and historical headcount growth trends.
* **Demographic Breakdown:** Deep dives into workforce distribution by age groups, gender balance, education level, and marital status.
* **Organizational Hierarchy:** Structural analysis across departments, business units, job roles, and geographic locations.

### 2. Attrition & Retention Analysis
* **Attrition Rates:** Calculation of voluntary vs. involuntary turnover rates, segmented by department, tenure, and performance tiers.
* **Predictive Risk Signals:** Identification of attrition hotspots (e.g., specific roles or managers with higher turnover rates).
* **Tenure Deep-Dive:** Analysis of employee survival rates and average lifespan within the organization to refine onboarding and retention milestones.

### 3. Recruitment & Talent Acquisition Pipeline
* **Time-to-Hire & Cost-per-Hire:** Efficiency metrics mapping the entire recruitment funnel from application to offer acceptance.
* **Source Effectiveness:** Evaluation of recruitment channels (e.g., LinkedIn, referrals, agencies) against long-term employee performance and retention.
* **Pipeline Funnel:** Visualization of applicant drop-off rates across interview stages.

### 4. Performance & Compensation Metrics
* **Performance vs. Compensation:** Correlation matrices mapping performance ratings (9-Box Grid) against salary compa-ratios to ensure fair and competitive compensation.
* **Promotion Metrics:** Tracking internal mobility rates, average time-to-promotion, and career progression fairness.
* **Training & Development:** Correlating completed training hours with subsequent performance improvements and promotion readiness.

---

## Data Model & Architecture
The dashboard is constructed on a optimized **Star Schema** to ensure fast query performance and scalable reporting:

* **Fact Table:** `Fact_HR_Changes` / `Fact_Active_Employees` (captures monthly snapshots, hires, terminations, promotions, and performance reviews).
* **Dimension Tables:**
    * `Dim_Employee`: Contains slowly changing attributes (SCD Type 2) like role, department, salary, and manager.
    * `Dim_Date`: A comprehensive calendar table enabling advanced Time-Intelligence calculations (YoY growth, rolling averages, YTD metrics).
    * `Dim_Recruitment`: Pipeline stages, vacancy details, and hiring sources.

---

## Advanced DAX Metrics Calculated
The report utilizes robust DAX formulas to power dynamic KPIs:
* **Active Headcount:** ```dax
  Active Headcount = 
  CALCULATE(
      COUNT(Dim_Employee[EmployeeID]),
      FILTER(
          Dim_Employee,
          Dim_Employee[HireDate] <= MAX(Dim_Date[Date]) &&
          (ISBLANK(Dim_Employee[TerminationDate]) || Dim_Employee[TerminationDate] > MAX(Dim_Date[Date]))
      )
  )
