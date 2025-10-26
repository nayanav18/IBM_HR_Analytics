#  HR Analytics – Employee Attrition Project (IBM HR Dataset)

##  Project Overview
This project analyzes employee attrition trends using the **IBM HR Analytics Employee Attrition Dataset**.  
It performs **Exploratory Data Analysis (EDA)** and builds an interpretable predictive model to identify key factors influencing attrition.  
The insights are further visualized through a **Power BI dashboard**, providing data-driven HR recommendations.

---

##  Technologies & Libraries Used
- **Python** – Data analysis and preprocessing  
- **Pandas** – Data manipulation and cleaning  
- **NumPy** – Numerical operations  
- **Matplotlib & Seaborn** – Data visualization  
- **SHAP** – Model explainability and feature importance visualization  
- **Power BI** – Dashboard and business insights visualization  

---

##  1. Data Import and Exploration
- Imported the IBM HR dataset and inspected structure using `df.head()`, `df.info()`, and `df.describe()`.  
- Verified dataset shape and column names using `df.shape` and `df.columns`.  
- Confirmed no missing or duplicate values.  
- Target variable (`Attrition`) contained two classes: **Yes** and **No**.

**Insight:**  
Dataset is clean, balanced, and ready for HR attrition prediction tasks.

---

##  2. Data Cleaning
- Removed redundant or constant columns: `EmployeeCount`, `EmployeeNumber`, `Over18`, `StandardHours`.  
- Verified final dataset shape and column integrity.

---

##  3. Categorical Feature Exploration
Explored key categorical variables:  
`BusinessTravel`, `Department`, `EducationField`, `Gender`, `JobRole`, `MaritalStatus`, `OverTime`, `WorkLifeBalance`, `JobSatisfaction`, etc.  

**Insight:**  
Features show diverse distributions and are well-suited for employee behavior analysis.

---

##  4. Correlation Analysis
- Generated a correlation heatmap for numerical columns.  
- Observed:
  - **Positive correlation** between `JobLevel` and `MonthlyIncome`.  
  - **Moderate correlation** between `YearsAtCompany` and `TotalWorkingYears`.  

**Insight:**  
These relationships indicate experience and level strongly influence income.

---

##  5. Feature Reduction
To simplify modeling, removed highly correlated or less-informative features:
`MonthlyIncome`, `TotalWorkingYears`, `YearsInCurrentRole`, `YearsSinceLastPromotion`, `YearsWithCurrManager`, `PerformanceRating`.

---

##  6. Visual EDA Insights

### **BusinessTravel**
- Frequent travelers show **higher attrition**.
> Heavy travel increases burnout risk.

### **Department**
- Sales and R&D show **higher attrition** than HR.
> These departments may need targeted retention programs.

### **EducationField**
- **Life Sciences** and **Technical Degree** fields show slightly higher attrition.
> Possible role mismatch or better external opportunities.

### **Gender**
- Attrition slightly higher in males but difference is minor.
> Gender not a key predictor.

### **JobRole**
- **Sales Executives** and **Research Scientists** show more attrition; **Managers** show less.
> Entry-level roles are less stable.

### **MaritalStatus**
- **Single employees** have highest attrition.
> Mobility and career change flexibility may drive this.

### **OverTime**
- Overtime workers have **significantly higher attrition**.
> Major burnout and work-life imbalance factor.

### **Years at Company**
- Attrition highest for employees with **0–5 years** at company.
> Early-tenure employees are more likely to leave.

### **Age**
- Younger employees (20–35 years) show higher attrition.
> Indicates need for better engagement for early-career staff.

---

##  7. SHAP Analysis (Model Explainability)
The **SHAP summary bar plot** ranks features by their mean contribution to model predictions.

| No. | Feature | SHAP Impact Description |
|-----|----------|--------------------------|
| 1 | **OverTime** | Strongest positive driver of attrition — overtime employees most likely to leave. |
| 2 | **JobSatisfaction** | Higher satisfaction reduces attrition likelihood. |
| 3 | **YearsAtCompany** | Longer tenure decreases attrition probability. |
| 4 | **WorkLifeBalance** | Better balance reduces attrition risk. |
| 5 | **Age** | Younger employees slightly more prone to attrition. |
| 6 | **DistanceFromHome** | Longer commute marginally increases attrition. |
| 7 | **Department** | Minimal impact compared to others. |

**Conclusion:**  
The most influential predictors of attrition are **OverTime**, **JobSatisfaction**, and **YearsAtCompany**.  
These findings make the model transparent and guide HR retention planning.

---

##  8. Dashboard Insights (Power BI)

### **Workforce Overview**
- **Total Employees:** 1,470  
- **Attrition Rate:** 16% (moderate turnover)  
- **Average Salary Hike:** 15.21%  
- **Total Monthly Rate:** 21M  

### **Key Visual Insights**
- **R&D Department:** Highest attrition share.  
- **Overtime Workers:** 16.12% of staff — highest risk group.  
- **Single Employees:** 45.78% attrition share.  
- **Age Group 25–40:** Core workforce with peak turnover between 25–35 years.

**Takeaways:**
- Focus retention efforts on:
  - **Young, early-tenure employees**
  - **Overworked staff**
  - **R&D and Technical roles**
- Improve work-life balance and engagement programs to curb attrition.

---

##  9. Final EDA Conclusions
- Dataset is clean, balanced, and model-ready.  
- Attrition strongly influenced by **OverTime**, **JobSatisfaction**, **WorkLifeBalance**, and **YearsAtCompany**.  
- Redundant features successfully dropped for optimal model performance.  
- SHAP ensures **model interpretability and fairness**.  
- Dashboard provides actionable business insights for **HR retention strategy**.

---

##  Author
**Nayana V**  

