# Palmoria Group HR Analysis

This project analyzes gender inequality  within Palmrex Group, a manufacturing company based in Nigeria.
The focus is to identify key issues related to gender disparity in salary, performance ratings, and departmental distribution,in order to provide insights and recommendations to management.

## Project Overview

The goal of this analysis is to help Palmoria Group:
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
  Salary Band = 
SWITCH(TRUE(),
    'Palmoria Group emp-data (1)'[Salary] <= 20000, "$10,000 - $20,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 30000, "$20,000 - $30,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 40000, "$30,000 - $40,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 50000, "$40,000 - $50,000",
    'Palmoria Group emp-data (1)'[Salary] <= 60000, "$50,000 - $60,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 70000, "$60,000 - $70,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 80000, "$70,000 - $80,000", 
    'Palmoria Group emp-data (1)'[Salary] <= 90000, "$80,000 - $90,000", 
    "$90,000 and above"
)

### Data Visualization:
1. Create the following visuals in Power BI:
2. Gender Distribution: Overall and broken down by region and department.
3. Performance Ratings by Gender: Analyze how ratings differ between genders.
4. Salary Distribution: Display salary distribution using salary bands, and compare by region and gender.


### Key Insights
1. Total Employees
Total Number of Employees: 874 employees in total.
2. Gender Distribution
Male Employees: 465 
Female Employees: 441
Unknown Gender: 40 employees
Insight: There is a slightly higher proportion of male employees in the company compared to female employees,
 but there is a notable portion of employees whose gender is not disclosed (Unknown).
3. Gender Distribution by Department
Some departments has unequal gender distribution amongst them , they have either more Males like the legal department with 49 males and 34 Females
or more females like the services department with 42 females and 37 males. Most departments tho have a balanced gender distribution.
Insight: Some departments show a male-dominated or a female-dominated workforce , while others like Human Resources are more gender-balanced.
 Diversity initiatives might be needed in any gender-dominated departments, particularly in technical and operational roles.
4. Gender Distribution by Location
Kaduna: 165 female employees and 182 male employees, totaling 361 employees.
Abuja: 158 female employees and 159 male employees, totaling 335 employees.
Lagos: 118 female employees and 124 male employees, totaling 250 employees.
Insight: The gender distribution across locations is relatively balanced, though the Kaduna region has a slightly higher proportion of males.
The gender distribution by region appears equitable, with no significant discrepancies between locations.








   
