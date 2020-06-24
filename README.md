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

A correlation matrix was built for the above parameters and the appraised value 2019. Appaised value correlated fairly well with home area and land area as expected.
The other parameters have no correlation against the others, meaning that they are no linear relationships between those variables.

![Figure2](Images/correlation_matrix.png)

To rank the neighborhoods,the following is the procedure used on homes valued less than $1MM
* 1- Sales, Crime Rate, School Rating, Acreage, SQ_FT, Flood Risk, where normalized first using the equation: Xn=(X-Xmin)/(Xmax-Xmin).
Where,  Xn= Normalized parameter
        X= Value of the parameter
        Xmin= minimum value of the parameter
        Xmax= maximum value of the parameter
* 2- Valuation can take negative numbers, so Vn=V/Vmax
Where,  Vn=normalized valuation
        V= valuation
        Vmax = maximum valuation
* 3-  Weights for each parameter can be defined based on user needs: How important each parameter is for the investor. Investor should rank parameters from 1 to 10, 
    1 meaning not important, 10 meaning very important
    For this example, we used:
    * Sales: 8
    * Crime Rate: 5
    * School Rating:	7
    * Acreage: 	6
    * SQ_FT: 	6
    * Flood Risk:	8
    * Valuation: 10
* 4- A score is defined based on the weights and the normalized parameters:
    Score: Wsales*Sales_norm + Wschools*School_norm + WAcreage*Acreage_norm + WSQ-FT * SQFT_norm + Wvaluation*Valuation_norm-W + Crime*Crime_norm - WFlood*Flood_norm
    Score is then normalized to have a range 0-100.
* 5-  Results are grouped by neighborhood, and neighborhoods that have negative valuation or no sales are removed.
* 6-  Valuation is normalized so score falls into 0-100 range.
* 7-  Results of top neighborhoods to invest given parameter importance and budget are presented, along with the map of where the neighborhoods are.

### Results
#### Investor Scorecard for all area of study
#### Investor Scorecard for budget $0-250k
#### Investor Scorecard for budget $250-500k   
#### Investor Scorecard for budget $500-750k  
#### Investor Scorecard for budget $750k-1M  


