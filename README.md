# Hospital Operations Performance Dashboard (Power BI)

**End-to-End Business Intelligence Project | Healthcare Operations (Simulated Case Study)**

**Tools:** Power BI, DAX, Excel, Data Modelling

<img width="1858" height="1046" alt="image" src="https://github.com/user-attachments/assets/ca0b714e-75b7-4f6f-9080-54c04eee1e19" />

---

## Table of Contents
1. [Business Context](#1-business-context)
2. [Problem Statement](#2-problem-statement)
3. [Project Objective](#3-project-objective)
4. [Business Requirements & KPI Framework](#4-business-requirements--kpi-framework)
5. [My Approach](#5-my-approach)
6. [Dashboard Overview](#6-dashboard-overview)
7. [Key Insights](#7-key-insights-based-on-the-dataset)
8. [Strategic Recommendations](#8-strategic-recommendations)
9. [Business Impact](#9-business-impact)
10. [Challenges & Limitations](#10-challenges--limitations)
11. [Future Improvements](#11-future-improvements)
12. [Skills Demonstrated](#12-skills-demonstrated)
13. [Repository Structure](#13-repository-structure)
14. [About Me](#14-about-me)

---

## 1. Business Context
HealthCare Plus, a busy urban hospital, is experiencing operational inefficiencies driven by rising patient volumes, inconsistent wait times, and limited visibility into diagnosis and demographic trends. Patient and visit data are stored separately, making it difficult for leadership to understand:

*   Which departments face the highest pressure
*   How patient demographics influence demand
*   When peak visit periods occur
*   Which diagnoses dominate each department

A centralised BI dashboard is required to support data-driven operational decisions.

---

## 2. Problem Statement
Hospital leadership lacks a unified view of:
*   Patient flow efficiency
*   Departmental performance
*   Bed and ward utilisation
*   Readmission patterns
*   Diagnosis trends
*   Demographic-driven demand

**Without these insights, the hospital risks:**
*   Understaffing during peak periods
*   Overloaded departments
*   Poor patient experience due to long wait times
*   Inefficient allocation of beds and treatment resources

---

## 3. Project Objective
To design and deliver a Power BI dashboard that consolidates patient and visit data into a single analytical view, enabling:
*   Faster operational decision-making
*   Improved patient flow
*   Better resource allocation
*   Clear visibility into diagnosis and demographic trends

---

## 4. Business Requirements & KPI Framework

| # | Business Requirement | Description | Business Value |
|---|----------------------|-------------|----------------|
| 1 | Patient Flow Efficiency | Calculate average wait time across all visits | Identifies bottlenecks and delays |
| 2 | Demographic Profiling | Categorise patients into age groups | Supports age-specific resource planning |
| 3 | Monthly Visit Trends | Track visit volumes over time | Enables staffing and capacity forecasting |
| 4 | Departmental Performance | Compare wait times and diagnoses by department | Highlights operational pressure points |
| 5 | Patient Type Distribution | Analyse inpatient vs outpatient mix | Supports bed and ward planning |
| 6 | Detailed Visit Analysis | Provide granular visit-level table | Enables clinicians to investigate cases |

---

## 5. My Approach

### 1. Requirement Translation → KPIs
Converted business questions into measurable KPIs:
*   Average Wait Time
*   Total Visits
*   Diagnosis Count
*   Inpatient vs Outpatient Ratio
*   Age Category Distribution

### 2. Data Validation & Preparation
*   Verified **Patient_ID** consistency across both tables.
*   Standardised categorical fields (Department, Diagnosis, Patient_Type).
*   Converted **Visit_Date** to proper date format.
*   Checked for outliers (e.g., extremely high wait times).

### 3. Data Modelling
Designed a 1-to-many relationship:
Patients[Patient_ID] 1 ——> * Visits[Patient_ID]

### 4. DAX Development
**Average Wait Time**

dax
Avg Wait Time := AVERAGE(Visits[Wait_Time_Min])

## Age Category
Age Category := 
SWITCH(
    TRUE(),
    Patients[Age] < 18, "<18",
    Patients[Age] <= 35, "18–35",
    Patients[Age] <= 60, "36–60",
    ">60"
)

## Monthly Visits
Total Visits := COUNTROWS(Visits)

## 5. Dashboard Design
KPI Cards: High-level summary of wait times, visits, and patient mix.

Line Charts: Temporal analysis for monthly volume trends.

Bar Charts: Comparative departmental performance and wait times.

Donut Charts: Visual breakdown of age categories.

Drill-through Table: Granular visit-level details for deep dives.

6. Dashboard Overview
The final solution provides a multi-faceted view of operations:

Executive KPIs: High-level health metrics.

Patient Flow: Bottleneck identification.

Departmental Performance: Efficiency by specialty.

Diagnosis Trends: Clinical volume breakdown.

Demographics: Targeted patient profiling.

7. Key Insights
Bottlenecks: Orthopedics and Cardiology exhibit the highest variability and longest wait times (exceeding 110 minutes in some cases).

Demographic Demand: Patients aged 60+ represent the largest user base, highlighting a need for chronic care optimization.

Pediatric Surge: High frequency of seasonal illnesses (Chickenpox, Flu) drive volume in Pediatrics.

Readmission Risk: Cardiology shows a significant "Readmission = Yes" trend, specifically linked to Heart Failure and Hypertension.

8. Strategic Recommendations
Dynamic Staffing: Reallocate resources to Orthopedics and Cardiology during peak wait-time windows.

Geriatric Pathways: Expand specialized care for the 60+ demographic to reduce readmission frequency.

Proactive Pediatrics: Implement seasonal staffing surges aligned with Flu/Chickenpox trends.

Clinical Monitoring: Establish post-discharge follow-ups for Cardiology patients to lower readmission rates.

Alert Systems: Integrate Power BI automated alerts for when wait times exceed a 60-minute threshold.

9. Business Impact
Operational Agility: Faster identification of resource gaps.

Experience: Targeted reduction in patient wait times.

Strategic Planning: Data-backed evidence for ward and bed allocation.

Forecasting: Visibility into seasonal diagnosis spikes.

10. Challenges & Limitations
The dataset is simulated, meaning real-world complexity (like emergency vs. elective surgery) is simplified.

Absence of real-time staffing data limits the ability to correlate wait times with specific employee shifts.

Lack of financial/cost-per-visit data prevents ROI analysis.

11. Future Improvements
Predictive Analytics: Use machine learning to forecast next month's patient volume.

Staffing Integration: Incorporate HR data to analyze staff-to-patient ratios.

Sentiment Analysis: Integrate patient satisfaction survey scores.

12. Skills Demonstrated
Technical: Data Modelling, DAX, Power Query (M), Data Visualization.

Domain: Healthcare Operations, KPI Framework Design.

Soft Skills: Analytical Storytelling, Strategic Thinking.

13. Repository Structure
Bash
├── data
│   ├── patients.csv            # Raw patient demographic data
│   ├── visits.csv              # Hospital visit transaction logs
│   └── data_dictionary.xlsx    # Metadata and field descriptions
├── pbix
│   └── Hospital_Operations.pbix # Final Power BI Project file
├── screenshots                 # Dashboard previews
└── README.md                   # Project documentation
14. About Me
[Your Name]

[LinkedIn Profile]

[Portfolio Website]

[Email Contact]
