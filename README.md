# Atlas Labs HR Dashboard in Power BI
We will be exploring a dataset for a fictional software company called Atlas Labs.

## Project Overview
We will be exploring a dataset for a fictional software company called Atlas Labs.

Atlas Labs HR team want to be able to monitor key metrics on employees. Their secondary goal is to understand what factors impact employee attrition.

The goal is to provide insights into employees’ demographics, attrition rates, and performance to help the HR team make data-driven decisions.

The dataset includes five CSV files: EducationLevel, Employee, PerformanceRating, RatingLevel, SatisfiedLevel.

## Data Preparation
### Cleaning and transforming the data
The data was cleaned and transformed using Power Query Editor. The following steps were taken during the data preparation phase:

- Added a prefix to datasets: Fact for fact table and Dim for dimension tables
- Reordered columns to improve organization and readability
- Removed irrelevant columns and rows
- Created two conditional columns: one with age ranges and another with distance from home in km ranges
- Created a full name column by concatenating the first name and last name columns

### Creating a dedicated date table
As a common practice, a dedicated date table was created in DAX to enable date intelligence. The use of a dedicated date table in DAX is a best practice that enables the creation of time-based calculations and analysis in Power BI, making it an essential step in the data preparation process. Here is the DAX code used to create the DimTable.

### Modelling the data
After that, the connections between the tables were established to prepare the data for the Power BI model.

The *Fact PerformanceRating* table is linked to the *Dim SatisfiedLevel* table through four connections, with the Environment Satisfaction and SatisfactionID being an active connection, while JobSatisfaction, RelationshipSatisfaction, and WorkLifeBalance are inactive connections.

The *Fact PerformanceRating* table is also connected to the *Dim RatingLevel* table through two connections, with the SelfRating and RatingID being an active connection, while ManagerRating and RatingID are an inactive connection.

The *Fact PerformanceRating* table is connected to the *Dim Date* table through one active connection, using the ReviewDate and Date fields.

The *Fact PerformanceRating* table is also connected to the *Dim Employee* table through one active connection, using the EmployeeID field, which has the same name in both tables.

The *Dim Employee* table is linked to the *Dim Date* table through one inactive connection, using the HireDate and Date fields.

Finally, the *Dim Employee* table is connected to the *Dim EducationLevel* table through one active connection, using the Education and EducationLevelID fields.

By establishing these table connections, the data is properly structured and linked, allowing for accurate and efficient analysis in the Power BI model. It is important to ensure that these connections are correctly set up to avoid errors or inaccuracies in the analysis.

### Creating the measures
In total, sixteen measures were made to create the dashboard:

The DAX code for each measure can be found in this link.

## Dashboard Overview
The dashboard consists of four pages, each focusing on a different aspect of HR analysis. The pages are:

**Overview**: This page provides an overview of the principal HR metrics, including headcount, attrition rate, number of inactive employees. The page includes visuals such a column chart that shows the number of employees by department and job role.

**Demographics**: This page displays employee demographics information, including age range, education level, gender, marital status. The page includes charts to help the HR team understand the diversity of the workforce and identify areas for improvement.

**Attrition**: This page provides information about attrition, including the possible reasons for leaving and the tenure of employees who left. The page includes a visual that shows the attrition rate by department and attrition rate by distance from home to work in KM.

**Performance**: This page displays last and next review date for each employee, as well as all ratings in previous reviews.

All visualizations are interactive, allowing the HR team to filter and drill down into the data.

## Conclusion
### Summary of the key insights taken from the dashboard
- The largest department is Technology
- The current Attrition Rate is 16.1%
- The majority of employees consider themselves white, with an average salary of $119.644. American Indian and Alaska Native employees have the lowest average salary at $107.381, which is 15.64% lower than the highest salary, which is $127.292, held by Native Hawaiian employees.
- More than half of the employees (56%) were between the ages of 20 and 29. On average, the salary for this age group was $79,899.
- 74% of attrition occur with employees who have some need for overtime.
- Employees who travel frequently have the highest attrition rate (24.9%), while those who do not travel have a attrition rate of 8%.
- The Sales department has the highest attrition rate, at 20.6%. Within that department, the Sales Representative role has the highest attrition rate at 39.8%. It is worth noting that the Human Resources department has a 19% attrition rate, with the Recruiter role having the highest rate at 37.5%.
- Employees with up to two years in the company have the highest attrition rates, at 31.2% and 34.5%. After the third year, the rate drops almost every year.

### Limitations and Future Improvements
The current dashboard provides useful insights into the company’s overall performance and employee-related metrics. However, there are further improvements that can be made to enhance the effectiveness of the dashboard.

Firstly, it would be beneficial to create measures and visuals that help to view the performance and evaluations by department. This would allow stakeholders to identify areas where improvements are needed, as well as areas where certain departments are excelling.

## References
The following resources were used to develop the Power BI project:

DataCamp: https://www.datacamp.com/

Power BI documentation: https://docs.microsoft.com/power-bi/

Power Query Editor documentation: https://docs.microsoft.com/power-query/

Power BI Community: https://community.powerbi.com/

LOGO: https://logo.com/
