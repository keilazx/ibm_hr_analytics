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
🔗 [https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

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
- The dashboard was developed in Power BI following prioritizing clarity and decision support for HR managers.
- The dashboard was structured into three thematic pages: Overview, Demographics, and Employee Experience. This allows users to progress from high-level diagnosis to root-cause exploration.
- The development process focused on translating HR business questions into measurable indicators
- Key design principles applied:
- - Attrition Rate was used as the primary metric across visuals to normalize comparisons between employee groups of different sizes.
- - Raw employee counts were included only as contextual information (tables, tooltips, KPIs).
- -  Conditional formatting was applied selectively to highlight critical risk levels without overwhelming the user.


## Screenshot
<img width="800" alt="Modeling" src="https://github.com/user-attachments/assets/cb725f70-9269-4bce-a87b-a8f426de8ca9" />
<img width="800" alt="Overview without filter" src="https://github.com/user-attachments/assets/ae6748c8-8316-4989-a495-7d3e556d279b" />
<img width="800" alt="Overview with filter" src="https://github.com/user-attachments/assets/0c0f3c8b-a556-4d46-9e80-0b63eaba75b1" />



## Dashboard link


## Key Insights
1. Holiday vs. Non-Holiday Weeks
- Holiday weeks consistently produce lower average sales across all years.
- This suggests inventory, staffing, or promotional strategies during holiday periods may require review.
2. Performance Variability Across Stores
- Significant disparities exist:
- - Top-performing stores exceed $300M in total sales
- - Lower-performing stores fall below $80M
- This highlights opportunities to investigate best practices and support struggling locations.

3. Impact of External Factors
- Temperature, fuel price, CPI, and unemployment showed no strong correlation with weekly sales.
- Internal drivers—such as store operations, assortment, pricing, or regional customer behavior—may be more influential.

## Recommendations
- Adjust inventory planning, staffing, or marketing efforts to improve holiday period performance.
- Identify operational differences that may explain large sales gaps.
- Since external factors show little correlation, prioritize pricing, merchandising, and in-store experience improvements.
- Enhance forecasting models: Incorporate internal metrics (store size, traffic, promotions) that may better explain variability.
