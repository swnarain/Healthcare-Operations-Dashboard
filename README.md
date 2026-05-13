# Hospital Operations Performance Dashboard (Power BI)

**End-to-End Business Intelligence Project | Healthcare Operations (Simulated Case Study)**

**Tools:** Power BI, DAX, Excel, Data Modelling

#### Business Outcome

This project demonstrates how business intelligence can be used to optimise hospital operations, reduce patient wait times, and support data-driven healthcare decision-making.

---

<img width="1858" height="1046" alt="image" src="https://github.com/user-attachments/assets/ca0b714e-75b7-4f6f-9080-54c04eee1e19" />

---

## Table of Contents

1. [Business Context](#1-business-context)  
2. [Problem Statement](#2-problem-statement)  
3. [Project Objective](#3-project-objective)  
4. [Business Requirements & KPI Framework](#4-business-requirements--kpi-framework)  
5. [Project Approach](#5-approach)  
   - [Requirement Translation → KPIs](#1-requirement-translation--kpis)  
   - [Data Validation & Preparation](#2-data-validation--preparation)  
   - [Data Modelling](#3-data-modelling)  
6. [DAX Development](#6-dax-development)  
7. [Dashboard Design](#7-dashboard-design)  
8. [Dashboard Overview](#8-dashboard-overview)  
9. [Hospital Operations Performance Key Insights](#9-hospital-operations-performance-key-insights)  
   - [Overall Operational Efficiency](#1-overall-operational-efficiency-average-wait-time)  
   - [Demographic Demand](#2-demographic-demand-age-category-distribution)  
   - [Patient Volume & Seasonality](#3-patient-volume--seasonality-monthly-trends)  
   - [Departmental Bottlenecks](#4-departmental-bottlenecks-avg-wait-times-by-dept)  
   - [Clinical Focus Areas](#5-clinical-focus-areas-most-common-diagnosis-by-dept)  
   - [Service Mix](#6-service-mix-inpatient-vs-outpatient-distribution)  
   - [Granular Clinical Oversight](#7-granular-clinical-oversight-detailed-patient-table)  
10. [Strategic Recommendations](#10-strategic-recommendations)  
11. [Business Impact](#11-business-impact)  
12. [Challenges & Limitations](#12-challenges--limitations)  
13. [Future Improvements](#13-future-improvements)  
14. [Skills Demonstrated](#14-skills-demonstrated)  
15. [About Me](#15-about-me)
    
---

## 1. Business Context

HealthCare Plus, a busy urban hospital, is experiencing operational inefficiencies driven by rising patient volumes, inconsistent wait times, and limited visibility into diagnosis and demographic trends. Patient and visit data are stored separately, making it difficult for leadership to understand:

*   Which departments face the highest pressure?
*   How patient demographics influence demand?
*   When peak visit periods occur?
*   Which diagnoses dominate each department?

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

## 5. Approach

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

---

## 6. DAX Development

- **Average Wait Time**

Avg Wait Time := AVERAGE(Visits[Wait_Time_Min])

- **Age Category**

Age Category = 
    SWITCH( 
        TRUE(), 
        'Patients'[Age] < 18, "<18", 
        'Patients'[Age] <= 35, "18–35", 
        'Patients'[Age] <= 60, "36–60", 
        ">60" 
    )

- **Monthly Visits**

Total Visits := COUNTROWS(Visits)

---

## 7. Dashboard Design

* **KPI Cards:** High-level summary of wait times, visits, and patient mix.

* **Line Charts**: Temporal analysis for monthly volume trends.

* **Bar Charts**: Comparative departmental performance and wait times.

* **Donut Charts**: Visual breakdown of age categories.

* **Drill-through Table:** Granular visit-level details for deep dives.


## 8. Dashboard Overview

The final solution provides a multi-faceted view of operations:

* **Executive KPIs:** High-level health metrics.
* **Patient Flow**: Bottleneck identification.
* **Departmental Performance**: Efficiency by specialty.
* **Diagnosis Trends**: Clinical volume breakdown.
* **Demographics**: Targeted patient profiling.


## 9. Hospital Operations Performance Key Insights

### 1. Overall Operational Efficiency (Average Wait Time)


**Data Point:** The hospital-wide average wait time is approximately 45 minutes.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/52c1155b-a68c-4731-bfd2-6138460f3ab3" 
    width="35%" 
    border="1"
  />
</p>

**Insight:** While the general average is within acceptable hospital benchmarks, the high variability between departments suggests that "average" does not tell the whole story. Success is currently dependent on which department a patient enters rather than a unified hospital standard.





### 2. Demographic Demand (Age Category Distribution)

**Data Point:** The largest patient segment is the Geriatric group (>60), followed by a significant Pediatric volume.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/6e623569-a53f-49fc-8ff2-c7741722e528" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** The hospital is primarily serving a high-complexity elderly population. This demographic typically requires longer consultation times and more frequent inpatient admissions, which directly impacts bed turnover rates and overall hospital capacity.





### 3. Patient Volume & Seasonality (Monthly Trends)

**Data Point:** Visit volumes fluctuate significantly month-to-month, with visible peaks in specific periods.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/05dfc4c3-7677-4975-8db8-e275d5ac66d7" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** The hospital experiences seasonal surges. By identifying these peaks, management can move away from static staffing to a predictive staffing model—increasing nursing and administrative support during high-volume months to prevent wait-time spikes.





### 4. Departmental Bottlenecks (Avg Wait Times by Dept)

**Data Point:** Orthopedics and Pediatrics consistently exhibit the highest average wait times (often exceeding 50–60 minutes).

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/236edc43-2e5a-4a4a-80cf-46bc90ca373d" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** These departments are the primary operational bottlenecks. High wait times in Pediatrics are likely due to high volume, whereas in Orthopedics, it likely stems from the complexity of treatments (e.g., surgeries/casts). These two areas require urgent resource intervention.





### 5. Clinical Focus Areas (Most Common Diagnosis by Dept)

**Data Point:** Hypertension dominates Cardiology, while Flu and Chickenpox drive Pediatric volume.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/fd9b3e65-9c0c-41e3-8873-d6d71dda0015" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** The hospital's clinical workload is split between chronic disease management (Cardiology/Neurology) and acute infectious diseases (Pediatrics). This suggests a need for specialized Chronic Care pathways for adults to reduce the load on the main emergency/visit rooms.





### 6. Service Mix (Inpatient vs. Outpatient Distribution)

**Data Point:** A significant portion of visits result in Inpatient stays, particularly for older age groups.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/926ca502-166b-46b8-a057-32f14b94339f" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** The high ratio of Inpatient to Outpatient visits indicates that HealthCare Plus is functioning as an acute care facility. Monitoring this mix is crucial for Bed Occupancy Management; if Inpatient stays rise without a change in bed count, ER wait times will inevitably increase.





### 7. Granular Clinical Oversight (Detailed Patient Table)

**Data Point:** Individual records show specific treatment types (e.g., Surgery vs. Medication) linked to specific wait times.

<p align="left">
  <img 
    src="https://github.com/user-attachments/assets/81537315-8215-4a33-944d-471f3a6520de" 
    width="48%" 
    border="1"
  />
</p>

**Insight:** The detailed table allows for Outlier Detection. By auditing the table, clinicians can identify specific cases where wait times exceeded 100 minutes to perform a Root Cause Analysis and prevent such delays from recurring.


---

## 10. Strategic Recommendations

* **Dynamic Staffing**: Reallocate resources to Orthopedics and Cardiology during peak wait-time windows.
* **Geriatric Pathways:** Expand specialized care for the 60+ demographic to reduce readmission frequency.
* **Proactive Pediatrics**: Implement seasonal staffing surges aligned with Flu/Chickenpox trends.
* **Clinical Monitoring:** Establish post-discharge follow-ups for Cardiology patients to lower readmission rates.
* **Alert Systems:** Integrate Power BI automated alerts for when wait times exceed a 60-minute threshold.

---

## 11. Business Impact

* **Operational Agility:** Faster identification of resource gaps.
* **Experience**: Targeted reduction in patient wait times.
* **Strategic Planning:** Data-backed evidence for ward and bed allocation.
* **Forecasting**: Visibility into seasonal diagnosis spikes.

---

## 12. Challenges & Limitations

*  The dataset is simulated, meaning real-world complexity (like emergency vs. elective surgery) is simplified.
*  Absence of real-time staffing data limits the ability to correlate wait times with specific employee shifts.
*  Lack of financial/cost-per-visit data prevents ROI analysis.

---

## 13. Future Improvements

* **Predictive Analytics**: Use machine learning to forecast next month's patient volume.
* **Staffing Integration**: Incorporate HR data to analyze staff-to-patient ratios.
* **Sentiment Analysis**: Integrate patient satisfaction survey scores.

---

## 14. Skills Demonstrated

- Power BI Dashboard Development
- DAX Measures & Calculated Columns
- Data Cleaning & Validation
- Data Modelling
- Healthcare KPI Analysis
- Business Intelligence Storytelling

---

## 15. About Me

Sweta Narain

Linkedin: https://www.linkedin.com/in/sweta-analyst/
