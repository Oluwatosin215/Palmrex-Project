

<img width="338" height="222" alt="Screenshot 2025-07-24 191449" src="https://github.com/user-attachments/assets/d4f3d0cd-54aa-47d4-986c-a09c411927e2" />

# Palmrex Group HR Analysis
This project analyzes gender inequality  within Palmrex Group, a manufacturing company based in UK.
The focus is to identify key issues related to gender disparity in salary, performance ratings, and departmental distribution,in order to provide insights and recommendations to management.

## Project Overview

The goal of this analysis is to help Palmrex Group:
- Identify gender distribution across regions and departments.
- Investigate performance ratings by gender.
- Examine the gender pay gap within the company.
- Provide insights into employee salary bands.

This analysis uses HR data of Palmrex Group, and the findings will be presented using various data visualizations in Power BI.

## Project Structure

- **Data**: The dataset contains columns like `Name`, `Gender`, `Department`, `Salary`, `Location`, and `Rating`. It provides details about employees across different regions and departments.
- **Analysis**: The analysis includes gender distribution, salary comparison
- **Visualization**: Power BI visualizations include bar charts, stacked bar charts, and salary band distributions.

## Data Cleaning and Preprocessing

### Steps for Data Cleaning:
1. **Handling Missing Gender Data**:
   - Employees with missing gender data were assigned a default value of "Unknown".
2. **Removing Employees Without Salary**:
   - Employees who no longer work at the company (without salary data) were removed.
3. **Removing Rows with NULL Departments**:
   - Any rows where the department value was `NULL` were removed.
4. **Fixing Salary Data**:
   - The Salary column was converted to a numeric data type to enable accurate salary band calculations.
   - Any non-numeric values or formatting issues were cleaned.

### DAX Calculations:
- **Salary Bands**: 
   A new calculated column was created to categorize employees into salary bands (e.g., "$10,000 - $20,000", "$20,000 - $30,000", etc.).
   
   Example DAX formula used:
   ```DAX
  Salary Band = SWITCH(TRUE(),
     'Palmoria Group emp-data (1)'[Salary] <= 20000, "10k - 20k", 
    'Palmoria Group emp-data (1)'[Salary] <= 30000, "20k - 30k", 
    'Palmoria Group emp-data (1)'[Salary] <= 40000, "30k - 40k", 
    'Palmoria Group emp-data (1)'[Salary] <= 50000, "40k - 50k",
    'Palmoria Group emp-data (1)'[Salary] <= 60000, "50k - 60k", 
    'Palmoria Group emp-data (1)'[Salary] <= 70000, "60k - 70k", 
    'Palmoria Group emp-data (1)'[Salary] <= 80000, "70k - 80k", 
    'Palmoria Group emp-data (1)'[Salary] <= 90000, "80k - 90k", 
    "90k and above"
)

### Data Visualization:
1. Create the following visuals in Power BI:
2. Gender Distribution: Overall and broken down by region and department.
3. Performance Ratings by Gender: Analyze how ratings differ between genders.
4. Salary Distribution: Display salary distribution using salary bands, and compare by region and gender.


### Key Insights
#### 1. Total Employees
Total Number of Employees: 874 employees in total.

#### 2. Gender Distribution
Male Employees: 465 
Female Employees: 441
Unknown Gender: 40 employees
Insight: There is a slightly higher proportion of male employees in the company compared to female employees,
 but there is a notable portion of employees whose gender is not disclosed (Unknown).
 
#### 3. Gender Distribution by Department
Some departments has unequal gender distribution amongst them , they have either more Males like the legal department with 49 males and 34 Females
or more females like the services department with 42 females and 37 males. Most departments tho have a balanced gender distribution.
Insight: Some departments show a male-dominated or a female-dominated workforce , while others like Human Resources are more gender-balanced.
 Diversity initiatives might be needed in any gender-dominated departments, particularly in technical and operational roles.
 
#### 4. Gender Distribution by Location
Kaduna: 165 female employees and 182 male employees, totaling 361 employees.
Abuja: 158 female employees and 159 male employees, totaling 335 employees.
Lagos: 118 female employees and 124 male employees, totaling 250 employees.
Insight: The gender distribution across locations is relatively balanced, though the Kaduna region has a slightly higher proportion of males.
The gender distribution by region appears equitable, with no significant discrepancies between locations.

#### 5. Performance Ratings by Gender
Very Good: A higher number of females 49 are rated Very Good, compared to 36 males.
Good: 82 males and 89 females rated Good.
Poor: 70 males are rated Poor, whereas 58 females are rated Poor.
Average: 212 males and 190 females rated as Average.
Insight: There is a disparity in performance ratings: a higher number of males are rated as "Poor" compared to females, suggesting that males may be underperforming in some areas. Also, more females are rated as "Very Good" which may indicate issues with evaluation processes in the form of potential gender bias or more Females are Perfprming better.

#### 6. Salary Distribution by Gender
90k+ Salary Band: 152 males and 126 females are in this band, showing a clear gender disparity at the higher salary levels.
70k-80k Salary Band: There are 54 males and 56 females, showing more balanced distribution.
30k-40k Salary Band: This band shows a more females in this salary band, with 41 males and 58 females.
20k-30k Salary Band: This band is also more balanced with 15 males and 13 females.
Insight: A  slight gender pay gap is evident at the higher salary levels, majorly in the 90k+ salary band, where a larger proportion of male employees occupy higher-paying positions. This suggests that management should consider conducting a salary audit and review promotion practices to ensure gender equality in salary distribution.

#### Recommendations for Management:
* Address Gender Pay Gap:
    1. Review salary distributions, particularly at higher levels, and take corrective actions to ensure equitable pay for both male and female employees.
    2. Focus on ensuring equal pay for employees in the same roles across all gender groups.

* Gender Diversity in Departments:
    1. Encourage gender diversity in male-dominated departments or female-dominated departments by implementing targeted recruitment initiatives and offering mentorship opportunities
    2. Review hiring practices to ensure that diversity is encouraged in traditionally male-dominated departments.
 

Below is the Dashboard
