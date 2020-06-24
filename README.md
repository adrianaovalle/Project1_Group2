# Houston Real Estate Investment Scorecard

## Motivation & Summary
### The Problem
Real Estate Investment opportunities require extensive research and Investors spend hours searching for best places to invest in Houston. Multiple apps are available for single properties, not for neighborhood trends. Access to large datasets is expensive and data analysis is time consuming for general public.

### The Question
What are the best neighborhoods to invest in Single Family Homes in Houston?

### The Solution
* Analysis of 8 parameters by neighborhood in selected Zip Codes
* Ranking of neighborhoods depending on investor budget


## Target Area
The focus of the study are Single Family Homes in 9 ZIP codes in the Houston area that are located in the inner loop between I-10, 610, and 288 highways.
The 9 ZIP Codes of study are: 77002,77005,77006, 77019,77025, 77030, 77054, 77027, 77098.

![Figure1](Images/Area_of_Study.png)



## Data Sources & File Management
The following are the data sources used:
* HCAD System: https://pdata.hcad.org/download/2019
* School Ratings: https://rptsvr1.tea.texas.gov/perfreport/account/index.html
* National Flood Data: http://nationalflooddata.com/flood/floodapi/
* Places:https://cloud.google.com/maps-platform/
* Crime: https://www.houstontx.gov/police/cs/Monthly_Crime_Data_by_Street_and_Police_Beat.htm

All related files to this project are located at: XXXX

## Data Gathering & Cleanup
Code:

## Data Analysis
Code:

## Investment Dashboard
Code: Results.ipynb
This code computes and summarizes the investment ranking by Neighborhoods in selected ZIP codes.

### Methodology
7 parameters were chosen to rank the best neighborhoods to invest depending on budget: 
* Sales: number of sales in 2019 in a given neighborhood
* Crime Rate: number of crimes in a given ZIP Code
* School Rating:	Average school rating for public elementary, middle and high-schools
* Acreage: 	Land area of the properties
* SQ_FT: 	House area in sqt
* Flood Risk:	Risk of flooding
* Valuation: Increase/ Decrease on home valuation year over year (2018-2019) 

A correlation matrix was built for the above paramters and the appraised value 2019.

![Figure2](Images/correlation_matrix.png)




