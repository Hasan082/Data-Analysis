# Analyzing a Real-World Dataset with SQL and Python

### Objectives
After completing this analysis, you will be able to:
- Understand a dataset of selected socioeconomic indicators in Chicago.
- Store data in an SQLite database.
- Solve example problems to practice your SQL skills.

### Dataset Overview
The dataset, "Selected Socioeconomic Indicators in Chicago," includes socioeconomic data for each Chicago community area from 2008 to 2012. It contains six key indicators and a "hardship index," with values ranging from 1 to 100. A higher hardship index indicates greater hardship.

### Dataset Variables
- **Community Area Number (`ca`)**: Unique identifier for each community area.
- **Community Area Name (`community_area_name`)**: Name of the community area.
- **Percent of Housing Crowded (`percent_of_housing_crowded`)**: Percentage of housing units with more than one person per room.
- **Percent Households Below Poverty (`percent_households_below_poverty`)**: Percentage of households below the federal poverty line.
- **Percent Aged 16+ Unemployed (`percent_aged_16_unemployed`)**: Percentage of people over 16 years old who are unemployed.
- **Percent Aged 25+ without High School Diploma (`percent_aged_25_without_high_school_diploma`)**: Percentage of people over 25 years old without a high school diploma.
- **Percent Aged Under 18 or Over 64 (`percent_aged_under_18_or_over_64`)**: Percentage of the population under 18 or over 64 years old.
- **Per Capita Income (`per_capita_income_`)**: Estimated per capita income for the community area.
- **Hardship Index (`hardship_index`)**: Composite score of the six socioeconomic indicators.

### Steps Performed

#### 1. Loading SQL Magic and Connecting to Database
We started by loading the SQL magic extension and connecting to an SQLite database using the following command:
```python
%sql sqlite:///DatabaseName.db
```
Where `DatabaseName.db` is the SQLite database file.

#### 2. Storing Data in SQLite Database
- We loaded the dataset into a Pandas DataFrame.
- Created a table in the SQLite database and inserted the data from the DataFrame.

#### 3. Basic SQL Queries
We performed several SQL queries to analyze the dataset, including:
- Retrieving data for specific community areas.
- Calculating the average per capita income.
- Finding the community area with the highest hardship index.

### Example Queries

#### Query 1: Retrieving Community Area Names
```sql
SELECT community_area_name FROM socioeconomics;
```

#### Query 2: Calculating Average Per Capita Income
```sql
SELECT AVG(per_capita_income_) FROM socioeconomics;
```

#### Query 3: Finding Community Area with Highest Hardship Index
```sql
SELECT community_area_name FROM socioeconomics
WHERE hardship_index = (SELECT MAX(hardship_index) FROM socioeconomics);
```

### Analysis and Insights
- We analyzed the distribution of the `hardship_index` across community areas.
- Identified key areas with higher socioeconomic challenges.
- Used SQL to derive insights and validate our understanding of the dataset.

### Conclusion
This lab provided hands-on experience in analyzing a real-world dataset using SQL and Python. We practiced SQL queries to explore and understand socioeconomic indicators in Chicago, gaining insights into community challenges and socioeconomic conditions.

### Dependencies
- Python 3
- Jupyter Notebook
- Pandas
- SQLite
- SQLAlchemy
- ipython-sql

### How to Run
1. Open the Jupyter Notebook.
2. Run each cell sequentially to perform the analysis.
3. Modify SQL queries as needed to explore additional insights.

### License
This project is licensed under the MIT License.

### Author
Md Hasanuzzaman

