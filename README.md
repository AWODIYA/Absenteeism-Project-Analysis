## Absenteeism Analysis

### Project Overiview
I’m preparing absenteeism data so it’s clean and structured for the data scientist. The goal is to make it easier to spot patterns, predict future absences, and provide insights that can help reduce unnecessary absenteeism.

### Data Sources
The primary dataset used for this analysis is the "Absenteeism-data.csv" file containing detailed information about the factors contributing to the lateness of each worker in an organization

### Tools
- Pyhton and pandas libraries  - Data Preprocessing and analysis
- Jupyter notebook(Anaconda) - for running code, testing, and documenting the workflow

### Data Cleaning/Preparation
For the initial data prepraration stage, I performed the following tasks:
1. Data loading and inspection
2. Handling missing values
3. Data Cleaning and formatting

### Data Analysis
Removed Irrelevant Column
- Dropped the ID column since it does not contribute useful information for predictions or insights
    -  ```python
       df = df.drop(['ID'], axis = 1)
- Encoded Categorical Feature (Reason for Absence)
Transformed the Reason for Absence column into dummy variables to represent each absence reason as binary indicators.
   - ```python
     reason_columns = pd.get_dummies(df['Reason for Absence'])
 -    Grouped Reasons into Categories: Simplified the 28 absence reasons into four major groups (Reason_1, Reason_2, Reason_3, Reason_4) by collapsing related dummy variables.
       ```python
     reason_type_1 = reason_columns.loc[:, '1':'14'].max(axis = 1).astype(dtype = int)])
     reason_type_2 = reason_columns.loc[:, 15:17].max(axis = 1).astype(dtype = int)
     reason_type_3 = reason_columns.loc[:, 18:21].max(axis = 1).astype(dtype = int)
      reason_type_4 = reason_columns.loc[:, 22:].max(axis = 1).astype(dtype = int)
 ### Results/Findings   
 1. The dataset was cleaned by removing the irrelevant ID column.
 2. The Reason for Absence column was one-hot encoded and grouped into four major categories.
 3. The final DataFrame includes both employee attributes and the new Reason_1 – Reason_4 features.
 4. Most records show zero absenteeism hours, with fewer cases of longer absences.
 5. The dataset is now well-structured and ready for statistical analysis and predictive modeling.

### References
1. [https://pandas.pydata.org/]
2. [https://www.udemy.com/]
      
