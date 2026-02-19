# 📊 Loan-Default-Risk-Analysis-PowerBI-Dashboard

## 🔗 Dashboard Overview

This Power BI dashboard provides a comprehensive analysis of loan distribution, applicant demographics, default trends, and financial risk metrics.  

It helps financial institutions:

- Identify high-risk borrower segments  
- Monitor default rate trends  
- Analyze credit score impact on loan distribution  
- Track Year-over-Year (YoY) loan and default changes  
- Make data-driven credit decisions  

The dashboard is divided into three major sections:

1. Loan Default & Overview  
2. Applicant Demographics & Financial Profile  
3. Financial Risk Metrics  

---

# 🧩 Problem Statement

Financial institutions face challenges in identifying risky borrowers and understanding default behavior patterns.  

This dashboard helps:

- Analyze loan amount distribution by purpose, age group, and credit score  
- Compare default rates across employment types  
- Identify high-risk income brackets  
- Monitor yearly loan growth and default fluctuations  

Using this dashboard, decision-makers can:

- Improve credit risk assessment  
- Optimize loan approval strategies  
- Reduce financial losses due to defaults  

---

# 📂 Dataset Information

The dataset includes the following attributes:

- Loan Amount  
- Loan Purpose  
- Credit Score Category  
- Employment Type  
- Income Bracket  
- Marital Status  
- Education Level  
- Age  
- Default Status  
- Year  

---

# ⚙️ Steps Followed

### Step 1: Data Loading
- Loaded dataset into Power BI Desktop (CSV format).

### Step 2: Data Cleaning
- Opened Power Query Editor  
- Checked column quality, column distribution & column profile  
- Removed null values from key financial columns  
- Verified correct data types  

### Step 3: Created Calculated Column (Age Group)

```DAX
Age Group = 
IF([Age] <= 25, "Teen",
IF([Age] <= 40, "Adults",
IF([Age] <= 60, "Middle Age Adults",
"Senior Citizens")))
```

### Step 4: Created Important Measures

**Total Loan Amount**

```DAX
Total Loan Amount = SUM(LoanData[LoanAmount])
```

**Default Rate %**

```DAX
Default Rate % = 
DIVIDE(
    CALCULATE(COUNT(LoanData[Default]), LoanData[Default] = "Yes"),
    COUNT(LoanData[LoanID])
) * 100
```

**YOY Loan Amount Change**

```DAX
YOY Loan Change = 
[Total Loan Amount] - 
CALCULATE([Total Loan Amount], PREVIOUSYEAR(LoanData[Date]))
```

---

# 📊 Dashboard Section 1: Loan Default & Overview

### Visuals Included:

- Loan Amount by Purpose  
- Average Income by Employment Type  
- Default Rate % by Employment Type  
- Average Loan Amount by Age Group  
- Default Rate % by Year  

### Key Insights:

- Home loans contribute the highest total loan amount.
- Unemployed individuals show the highest default rate.
- Full-time employees have the lowest default percentage.
- Default rate peaked around 2016.
- Adults and middle-aged borrowers receive higher loan amounts.

---

# 👥 Dashboard Section 2: Applicant Demographics & Financial Profile

### Visuals Included:

- Median Loan Amount by Credit Score Category  
- Average Loan Amount (High Credit) by Age Group & Marital Status  
- Total Loan (Adults) by Credit Score Bins  
- Loan Distribution by Dependents  
- Number of Loans by Education Type  

### Key Insights:

- Medium and High credit categories account for major loan distribution.
- Married applicants with high credit scores receive slightly larger loans.
- Bachelor’s degree holders have the highest number of loans.
- Adults contribute the highest loan volume among age groups.

---

# 📈 Dashboard Section 3: Financial Risk Metrics

### Visuals Included:

- YOY Loan Amount Change  
- YOY Default Loan Change  
- YTD Loan Amount by Credit Score & Marital Status  
- Income Bracket vs Employment Type Loan Distribution  

### Key Insights:

- Significant loan growth observed in 2015 and 2018.
- Default loans increased sharply in 2015.
- High-income borrowers contribute majority of total loan exposure.
- Loan exposure among employment types is relatively balanced.

---

# 🛠 Tools & Technologies Used

- Power BI Desktop  
- Power Query  
- DAX (Data Analysis Expressions)  
- Data Modeling  
- Interactive Filters & Slicers  

---

# 📌 Overall Conclusion

This dashboard provides a structured loan risk analysis framework that helps financial institutions:

- Identify high-risk borrower categories  
- Track loan growth trends  
- Analyze demographic-based credit behavior  
- Improve portfolio risk management  

The insights generated from this analysis support better credit policy decisions and financial planning strategies.

---

# 📷 Dashboard Snapshots

<img width="803" height="452" alt="image" src="https://github.com/user-attachments/assets/4774ca5b-a74c-4d36-964e-0260747d8530" />
<img width="797" height="452" alt="image" src="https://github.com/user-attachments/assets/32551e1d-a9cf-4c89-b7cd-61ee926221ee" />
<img width="800" height="454" alt="image" src="https://github.com/user-attachments/assets/e63c54b9-a39e-4dda-b940-6884fef66280" />



