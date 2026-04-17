# Healthcare-Operations-Dashboard
Business intelligence dashboard built in Power BI to analyse patient flow, demographics, and departmental performance for data-driven healthcare optimisation.

**1. Business Context**

HealthCare Plus, a busy urban hospital, is facing operational inefficiencies affecting patient wait times, departmental performance, and resource allocation. To support data‑driven decision‑making, the hospital requires a centralised dashboard that provides clear visibility into patient flow, demographics, and departmental trends.

This project demonstrates how business intelligence can transform raw patient and visit data into actionable insights for operational improvement.

**2. Problem Statement**
Hospital leadership lacks a unified view of patient flow, wait times, and departmental performance. Without timely insights, it becomes difficult to optimise staffing, reduce bottlenecks, and plan resources effectively.

This dashboard addresses these challenges by analysing patient demographics, visit patterns, wait times, and diagnosis trends.

**3. Project Objectives**
- Improve visibility into patient flow and wait time efficiency
- Understand demographic patterns to support resource planning
- Identify departmental bottlenecks and diagnosis trends
- Track monthly visit trends for staffing optimisation
- Provide a detailed, filterable view for deeper clinical analysis

**4. Data Model**
The dataset consists of two relational tables:

**Patients** — patient-level information (age, gender, patient type, etc.)
**Visits** — visit-level information (visit date, department, wait time, diagnosis, treatment type)

**Relationship**:  
Patients[Patient ID] 1 — many → Visits[Patient ID]

Use Visits.Patient ID for visit-level metrics (e.g., average wait time)
Use Patients.Patient ID for unique patient-level insights (e.g., demographics)

**5. Key DAX Measures & Calculations**
- [Screenshots]
  
**6. Dashboard Features**
**Patient Flow Efficiency**
- Overall average wait time across all departments
- Department-level wait time comparison to identify bottlenecks

**Patient Demographics**
- Age group distribution (%, count)
- Patient type breakdown: Inpatients vs Outpatients

**Trends & Resource Planning**
- Monthly visit trends to identify peak periods
- Supports staffing and scheduling decisions

**Departmental Performance**
- Diagnosis patterns by department
- Helps allocate medical resources and specialist availability

**Detailed Analysis Table**
Includes:
Patient ID
Visit date
Department
Treatment type
Diagnosis
Wait time

Filters:
Department
Time period
Patient type

**7. Key Insights)**

[in progress]

**8. Business Recommendations**
[in progress]

**9. Tools & Skills Demonstrated**
Power BI: Data modelling, DAX, interactive dashboards
Data Cleaning & Transformation: Power Query
Data Analysis: Trend analysis, segmentation, operational metrics
Business Intelligence Storytelling
Healthcare Operations Analytics

**10. Dashboard Preview**

**11. How to Use This Project**

Download the .pbix file
Open in Power BI Desktop
Ensure data paths are correct
Interact with filters to explore insights
