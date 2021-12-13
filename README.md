# ExcelChallenge

## Overview of Project

### Purpose
The goal of the project is to analyze theater campaign outcomes in relation to their launch dates and fund-raising goals in order to see which campaigns tend to be successful  

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
I created a pivot table to filter and organize my data. The data was filtered according to the month a theater campaign was launched. The total amount of successes, failures and calculations for each month were tabulated and then graphed using a line chart. See graph below. 

![Theater Outcomes vs. Launch](https://github.com/alexlieberman22/ExcelChallenge/blob/master/Resources/Theater_Outcomes_vs_Launch.png?raw=true)

### Analysis of Outcomes Based on Goals
I created a table to find the total amount of successes, failures and calculations based on financial goal amount from under $1000 to over $50000 in $5000 increments. To calculate these totals, I used the COUNTIFS function. 
for example:
```
=COUNTIFS(Kickstarter!$F:$F, "successful", Kickstarter!$D:$D, ">=10000", Kickstarter!$D:$D, "<14999",Kickstarter!$R:$R,"plays")
```
This function will count all cells containing the word "successful", with a goal between $10000 and 15000, among productions considered "plays". Each total in the table has a variant of this function. When calculating percentages, I used the IFERROR and Round function to better present the percentages and to avoid divide by 0 errors. 
for example:
```
=IFERROR(ROUND((C3/E3),2),0)
```
where C3 is a total amount failed and E3 is the total number of projects for the goal range in row 3. I then created a line chart of the percentages. See graph below.

![Outcomes vs. Goals](https://github.com/alexlieberman22/ExcelChallenge/blob/master/Resources/Outcomes_vs_Goals.png?raw=true)

### Challenges and Difficulties Encountered
The only difficulty I encountered was getting the formula right for the Number Successful column in Outcomes Based on Goals. Getting all the arguments to work right in the COUNTIFS function and having copy it over to the other cells without much editing took me some time to get right. Using the $ signs and putting my search criteria in quotation marks was the solution. 

## Results

- Conclusions about the Outcomes based on Launch Date
  - The summer months like May and June seem to have the most successful campaigns. Cancelations seem to be unaffected by time of year and are relatively quite low compared to the other outcomes 

- Conclusion about the Outcomes based on Goals
  - The campaigns that had a lower goal amount tended to be more successful. 

- Limitations of this dataset
  - For the Theater Outcomes by Launch date, this data only accounts for productions considered Theater, a broader sample set may give different results. It also doesn’t provide us with explanation as to why the summer months may be more successful. The accuracy of the data for Outcomes Based on Goals past $20000 is quite low because of low sample size, so nothing much can be concluded for very expensive campaigns. 

- Other possible tables and/or graphs 
  - We could've also compared year to success rate to see if campaigns have become more or less successful over time. 
  - Our range of goal amounts could have been less spread out, instead I could have compared outcomes between 0 and 10000 where most of the data points fall.
