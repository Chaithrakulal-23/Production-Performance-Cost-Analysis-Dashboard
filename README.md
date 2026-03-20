# Production Performance Dashboard


## Problem Statement

This dashboard helps analyze production performance across different regions, managers, and product types. It provides insights into production efficiency, cost distribution, and workforce characteristics such as age groups and gender.

The dashboard enables stakeholders to

 - Monitor total production cost by product type

 - Evaluate manager performance based on number of tasks handled

 - Track production trends over time (monthly & yearly)

 - Analyze cost efficiency through production cost per unit

 - Understand workforce distribution using gender and age groups

By using this dashboard, organizations can identify inefficiencies, optimize costs, and improve production planning.

### Steps followed 

Step 1 : Loaded dataset into Excel.

Step 2 : Applied filters (dropdowns) to all columns and checked for null values.

Step 3 : Identified null values in Gender column and replaced them with "Unknown".

Step 4 : Sorted Manager column and found data quality issue where the same manager had different ages.

Step 5 : Sorted Production Date in ascending order and considered the first recorded age of each manager as the correct age.

Step 6 : Used VLOOKUP to extract correct age for each manager
           
           =VLOOKUP(A2,'Production Dataset'!$D$1:$I$121,6,0)

![Snap_1](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 7 : Created a helper table and used VLOOKUP again to fill corrected age:

           =VLOOKUP(D2,vlookup!$A$2:$B$11,2,0)
![Snap_2](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 8 : Created a new column Age Group using IF condition

          =IF(I2<=35,"A1",IF(I2<=45,"A2","A3"))
![Snap_3](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 9 : Created Production Cost Per Unit column:

          Total Cost / Units Produced
![Snap_4](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 10 : Removed decimal places for better readability.

Step 11 : Created a pivot table to calculate the total production cost for each product type and visualized the results using a 3D column chart to clearly compare cost distribution across products.
![Snap_5](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 12 : Built another pivot table to count the number of production IDs handled by each manager, which helped in analyzing workload distribution, and represented this using a 3D bar chart for better clarity.
![Snap_6](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 13 : Developed a pivot table to analyze production trends over time by calculating units produced across different months and years, and displayed these trends using a line chart to identify patterns and fluctuations.
![Snap_7](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)

Step 14 : Created a pivot table to compute the average production cost per unit for each product type, and visualized this information using a pie chart to highlight cost efficiency differences.

![Snap_8](https://user-images.githubusercontent.com/102996550/174089602-ab834a6b-62ce-4b62-8922-a1d241ec240e.jpg)
Step 15 : Designed a dedicated dashboard sheet and added slicers for region, gender, age group, and production date to enable dynamic filtering and better user interaction.

Step 16 : Connected all slicers to the pivot tables and arranged the corresponding pivot charts within the dashboard, resulting in a fully interactive and user-friendly reporting interface.


# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://user-images.githubusercontent.com/102996550/174096257-11f1aae5-203d-44fc-bfca-25d37faf3237.jpg)

 


# Insights

A single page report was created on Excel.

Following inferences can be drawn from the dashboard;

### 1. Cost Analysis

Certain product types contribute more to total production cost

Indicates opportunities for cost optimization

### 2. Manager Performance

Some managers handle more production tasks than others

Workload distribution is uneven

### 3. Production Trends

Production varies across months and years

Helps identify peak production periods

### 4. Cost Efficiency

Production cost per unit varies by product type

Some products are more cost-efficient

### 5. Workforce Analysis

Age groups classified as:

A1 (≤35)

A2 (36–45)

A3 (>45)

Gender data cleaned for accurate reporting97 %)


         
