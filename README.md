# Tableau

## The Question: Is “Show Business” big business?

An investigation of Broadway Shows Cost, Revenue, and Attendance between 1995 and 2015

- What were the KPIs in 2015?
- Which Broadway shows were the greatest* in a specified time period?

NOTE: Greatest is defined within each visual, and includes consideration of gross revenue, average ticket price, number of
tickets sold, percent of seats filled, and total number of performances.

### Data Set and Preprocessing

Started with the Raw Dataset, a flat CSV file with 31,297 rows and 12 rows. Each row of the dataset holds data for a week
of performances for each show running at that time. The data set is from 1990 to 2015.
We corrected for data structure issues, including standardization, missing values, redundancies missed because of typos,
white space trimming, etc.
Lastly, manual data collection and use Python and a geocoding API to normalize theaters and enhance dataset for map visualizations.

[Data Preprocessing Steps Log](https://acrobat.adobe.com/id/urn:aaid:sc:us:689f62b3-c5ee-47bb-9cc5-5efb97d5a943)



### What You Will See

The files included in this repository are:
1. Broadway Tableau workbook
2. Excel EDA
3. Geolocation corrected data
4. Excel Final for Tableau Upload
5. Presentation Broadway dataset

### Data Dictionary

| Metric                    	| Description                                                                           	|
|-------------------------------|-------------------------------------------------------------------------------------------|
| Record ID                 	| Record number, assigned in raw data. One unique number per row.                       	|
| Full_Date                 	| Date of the last day of the week. Each date represents one week.                      	|
| Year                      	| Year of the performance                                                               	|
| BroadwayProduction        	| Name of Broadway show.                                                                	|
| Theater                   	| Name of theater where the show was hosted.                                            	|
| Address                   	| Address of the theater.                                                               	|
| Latitude and Longitude*   	| Location of the theater, calculated using a geocoding API.                            	|
| Weekly Performances       	| Number of individual shows in each week.                                              	|
| Weekly Attendance         	| Number of tickets sold in the given week, i.e., patrons in seats.                     	|
| PercentageOfCapacity      	| Percentage of total seats occupied by ticket holders.                                 	|
| Weekly Gross Revenue      	| Total box office sales for a performance or week.                                     	|
| Average Ticket Price      	| Average price of all tickets sold per week.                                           	|
| Average Price per Ticket* 	| `SUM([Weekly Gross Revenue]) / SUM([Weekly Attendance])`                               	|
| Avg Attendance Per Performance* | `SUM([Weekly Attendance]) / SUM([Weekly Performances])`                               	|
| Avg Available Seats Per Performance* | `SUM([Weekly Attendance]) / (AVG([Capacity(Percentage)]) * SUM([Weekly Performances]))` |
| Avg Gross Per Performance*	| `SUM([Weekly Gross Revenue])/SUM([Weekly Performances])`                              	|
| RevPAS*                   	| Revenue per Seat—total possible dollars for each seat.                                	|

![image](https://github.com/amrubinson/Tableau/assets/157393313/0b6147bc-6063-4ed4-956b-1e030f5f1b3a)


### Learning Process

This was a collaborative project between Carlos and was my first large project in Tableau. We tried to be mindful
of the accessibility, aesthetics, and simplicity of use of the worksheets and dashboards; however, we did find ourselves
getting sucked down different tangents that may not have been necessary to answer our questions.

In the end, we had three key take-aways:
1. Keep it simple stupid! (KISS)
For example, we converted capacity to a percentage when we could have used Tableau to show it as a percentage.

2. Leverage Tableau to do the heavy lifting.
Tableau has many powerful analysis, visual, and formatting options. Use them to investigate and highlight the key points
instead of independent analysis or mental gymnastics to get to the point. And, if you don't know how to do it, look it up.

3. Use visual storytelling to tell the customer's story.
Consider the customer’s perspective, what would be of interest to them, and insider metrics (i.e., RevPAS).
