# IBM HR Analytics Employee Attrition PowerBI Dashboard
---
## Overview 
This project presents an end-to-end HR analytics analysis of employee attrition using the IBM HR dataset in Power BI. The workflow includes sourcing the raw CSV data, performing data cleaning and feature engineering in Power Query, modeling fact and dimension tables, and developing an interactive dashboard from scratch. The purpose of this dashboard is to analyze workforce stability, identify high-risk employee segments, and understand how demographic, compensation, and employee experience factors relate to attrition.

## Business problem
This dashboard aims to support Walmart’s operational and merchandising decisions by answering key strategic questions:
- What is the overall turnover rate in the company?
- How is turnover distributed by department or role?
- Are there differences in turnover based on age or gender?
- Is there a relationship between salary and attrition?
- Are employees with certain salary ranges at greater risk of leaving?
- How does the salary level compare across departments and how does it correlate with turnover?
- Are employees with low satisfaction in their role, environment, or leadership more likely to leave?
- Do employees with fewer or more years in the position leave more?
- How does educational level impact turnover?
- Do employees with longer working hours have higher turnover?
- Is there a relationship between performance and employee satisfaction?
- What actions could reduce turnover in the most affected groups?


## Dataset
Dataset used for this analysis:
🔗 [ibm-hr-analytics-attrition-dataset](https://github.com/keilazx/ibm_hr_analytics/blob/c74c89cb07ee907d2cf04bdbbcf33d3b5a1ecde1/IBM%20HR%20Analytics.pdf)

## Methodology
1. Data cleaning & preparation (Power Query + DAX)
- Promoted the first row to headers and explicitly assigned data types to all variables (numeric, text).
- Converted key financial fields (e.g., MonthlyIncome) to numeric formats suitable for aggregation.
- Created a binary attrition flag to represent employee exits consistently across measures.

2. Feature engineering
- Created variables to support HR analytics and executive-level interpretation:
- - Demographic groupings
- - - Age range
- - - Salary range
- - - Tenure bands
- - Human capital indicators
- - - Translated numeric education levels into readable categories.
- - - Calculated a Global Satisfaction Score as the average of environment, job, and relationship satisfaction.
- - - Classified employees into engagement segments (At risk, Stable, Engaged) based on satisfaction thresholds.
- Removed unused columns to reduce model complexity and improve performance.

3. Data modeling
- Built a fact table (FACT_Empleados) containing employee-level measures and analytical attributes.
- Created a dimension table (DIM_Roles) combining Department and Job Role into a unique position key.
- Established a relationship between fact and dimension tables using a composite key (DIM_Position) to enable role- and department-level analysis while maintaining a star-schema structure.

4. Dashboard Development
- The dashboard was structured into three thematic pages: Overview, Demographics, and Employee Experience. This allows users to progress from high-level diagnosis to root-cause exploration.
- The development process focused on translating HR business questions into measurable indicators.
- Included a filter pane in the three pages, making it visible when clicked on the Filter button.
- Key design principles applied:
- - Attrition Rate was used as the primary metric across visuals to normalize comparisons between employee groups of different sizes.
- - Raw employee counts were included only as contextual information (tables, tooltips, KPIs).
- - Conditional formatting was applied selectively to highlight critical risk levels without overwhelming the user.


## Screenshot
<img width="800" alt="Modeling" src="https://github.com/user-attachments/assets/cb725f70-9269-4bce-a87b-a8f426de8ca9" />
<img width="800" alt="Overview without filter" src="https://github.com/user-attachments/assets/ae6748c8-8316-4989-a495-7d3e556d279b" />
<img width="800" alt="Overview with filter" src="https://github.com/user-attachments/assets/0c0f3c8b-a556-4d46-9e80-0b63eaba75b1" />


## Dashboard PDF link
🔗 [Link](https://github.com/keilazx/ibm_hr_analytics/blob/4fd546cdb7cac0849987ee12ac96d88c41da8be4/IBM%20HR%20Analytics.pdf)

## Key Insights
- The overall attrition rate is of 19%. The HR and Sales department's attrition rate is above the overall rate, with 24% and 26% respectively; whereas the Research and Development (R&D) has a 16% attrition rate.
- Employees in the age group of 18-29 had the highest attrition rate (39%). There is no significant difference between male and female  attrition rate, with the former having a 20% rate and the latter a 17% rate.
- There is a relationship between salary and attrition. People with an average salary below than $3,000 tend to have higher attrition rates which suggests that as salaries go up, the attrition rate falls under the 7% attrition rate. Nonetheless, people with an average income of $6,924 - which is above overall average monthly income - have an attrition rate of 21%.
- Education level shows a similar tendencies of attrition for staff with bellow college to master's degree, ranging from 17% to 22%. Those with Doctor have an attrition of 12%.
- Employees with less than 2 years working for the company have an attrition rate of 96%. Staff with over 2 years have an attrition that goes from 28% to 8% - this latter rate belongs to staff that have 20+ years working for the company.
- Employees who work overtime consistently show lower satisfaction levels and higher attrition risk compared to those who do not. The distribution skews heavily toward the “At risk” category among overtime workers, while “Engaged” employees are underrepresented.

## Recommendations
- Track early warning signals (overtime, low satisfaction, manager changes) specifically for new employees.
- Reassess salary competitiveness for employees earning below $3,000, especially in Sales and HR.
- Complement pay with non-monetary benefits (flexibility, learning budgets) where immediate salary increases are not feasible.
- Create clearer career paths, skill development programs, and internal mobility options for early-career talent.
- Increase feedback frequency and growth conversations for employees between 18-29.
- Strengthen engagement among high performers.
- High and very high performers showing “at risk” satisfaction signals suggest burnout or misaligned rewards.
- Introduce recognition, advancement opportunities, or role enrichment for top performers before dissatisfaction converts into attrition.
- Since attrition decreases at higher education levels, invest in upskilling and tuition support for existing employees.
