# Business Expansion Business Intelligence (BEBI Project)

## Project Overview
This project seeks to determine if opening a new training center on Lagos Island is a viable option, by analyzing data from current training programs and pinpointing areas where growth is possible

## Data Sources
The primary data source for this project is the BEBI (Business Expansion Business Intelligence) table.  BEBI is an appended dataset combining information from four existing training programs in Lagos:

- Lagos Data Analyst Weekend - Data on weekend training programs.
- Lagos Data Analyst Midweek - Data on weekday training programs.
- Lagos UI/UX - Data on UI/UX training programs.
- Lagos Cyber Security - Data on cybersecurity training programs.

## Tools 
- POWER BI

## Exploratory Data Analysis (EDA)
The following steps where taken to gain a better understanding of the BEBI data and uncover insights relevant to the project objectives.
1. Data Cleaning and Preparation
- Check for and handle missing values.
- Identify and address any data inconsistencies or errors.
- Transform data into appropriate formats for analysis (e.g., date formats, numerical conversions)

2. Descriptive Statistics:
- Calculate summary statistics (sum, average, standard deviation) for key variables like revenue, total number of registered candidates, location, program type, etc.
- Visualize data using stacked column charts, funnel, clustered bar charts and other relevant charts to understand the distribution of variables.

3. Location Penetration and leads Analysis:
- Analyze the geographic distribution of current training program candidates.
- Visualize Lagos location penetration using charts to identify areas with high and low participation.
- Calculate penetration rates for different areas of Lagos.
- Create an oppportunity type funnel identifying the leads.

4. Revenue Breakdown:
- Analyze revenue generation by existing Lagos LGA, monthly, and yearly.
- Identify top-performing locations and potential areas for improvement.
- Analyze the sales team performance in terms of revenue, registered and activated candidates.

5. Correlation Analysis:
- Explore potential correlations between program type, location, demographics, and revenue using a Line charts.

## Data Analyst 
I created a DataTable  from Timestamp column using the following syntax

`DateTable = ADDCOLUMNS(
CALENDAR(DATE(2021, 1, 1), DATE(2030, 12, 31))
"Year", YEAR([Date]),
"Month", FORMAT([Date], "MMM"),
"Month Number", MONTH([Date]),
"Quarter", "Q" & FORMAT(Quarter([Date]), "0"),
"Weekday", FORMAT([Date], "DDD"),
"Week NUmber", WEEKNUM([Date])`

To calculate TotaL Revenue: From the data we have three different installment plan therfore to get calculate the total revenue 

Total Revenue = `SUM(BEBI[1st installment]) + SUM(BEBI[2nd installment]) + SUM(BEBI[3rd installment])`

I then proceed to get the Payment Date Revenue using the payment date column
DAX

Payment Date Revenue = `CALCULATE([Total Revenue], 
                      USERELATIONSHIP('BEBI[Payment Date],
                      DateTable[Date]),
                      FILTER('DateTable', DateTable[Year] IN {2023 2024}))`


## Result/Findings
Based on my analysis, 
1. Analysis of the Lagos training center's performance reveals a consistent upward trend in revenue over the last year, culminating in a significant peak.
2. The Data Analyst program stands out as the top performer, driving the majority of this revenue growth.
3. Geographically, the Kosofe, Surulere, and Alimosho areas have demonstrated strong registration numbers and contributed significantly to the overall revenue.
4. A notable surge in UI/UX and Cybersecurity program enrollments occurred in October, likely due to a targeted promotion, such as a discount or marketing campaign.

## Recommendations
Based on the analysis, I recommend the following actions
1. Leveraging on the techniques and  strategies used by Deborah Toluwalope to improve performance of other mangers
2. Concentrate effort on lead generation during high performing days (Wednesday & Thursday), and month (August & October).
3. Given the high number of leads in the nurturing stage, implementing targeted nurturing campaigns could further boost conversions
4. Be mindful of seasomal variations and plan marketing and sales activities accordingly to maintain consistent performance
5. Expand to High-Performing Areas: Focus on Kosofe, Surulere, and Alimosho for new locations.
6. Optimize Training Sessions: Increase physical and weekend sessions to maximize engagement.
7. Leverage Top Managers: Use strategies from top-performing managers to improve overall team performance.

Considering the performance data, the next location should ideally be one with higher potential of growth and engagement. Based on the current trends Kosofe emerges as a strong location due to its high revenue, and registration number.
Additionally, expanding to other higher performing areas like Surulere and Alimosho could also be beneficial. In conclusion, strategically selecting one of these high performing areas, the project can maximize it's impact and continue to grow it's reach and revenue. 

## Limitations
During data preparation, blank rows in the 1st, 2nd , and 3rd installment and payment columns (which should contain decimal or whole numbers) were converted to zero values. This step was crucial for enabling calculations and analysis. 
However, despite this conversion and subsequent attempts to identify and remove outliers, a small number of outliers persist in the dataset. These remaining outliers, while few, could still potentially skew the results of the analysis and warrant careful consideration.

## References
1. [Class Ace](www.classace.ai)
2. github.com

😄
💻



