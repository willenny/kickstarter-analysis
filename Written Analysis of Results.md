# Kickstarting with Excel

## Overview of Project

### Purpose
By using Excel, its functions, and graphing capabilities we are able to help Louise compare how different her fundraising campaign was to other similar campaigns. Our main focus was to determine how her play 'Fever' fared in relation to launch dates and funding goals of other theather productions and plays. Using grpahs to present the data, we are now able to give analysis to Louise about her play.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

Using my knowledge of pivot tables and graphing in Excel, I visualized project outcomes of successful, failed, and canceled, based on their launch date. The launch date refers to the month that the fundraising campaign began. Due to originally only being given the launch date as a Unix timestamp, it was essential to convert this into a more easily read date. The following code successfully converted the Unix timestamp in a readable date. `=(((J2/60)/60)/24)+DATE(1970,1,1)`

Next, I created a pivot table from the KickStarter worksheet, and placed it in a new sheet labeled "Theater Outcomes by Launch Date." When organizing the pivot table, the data is best going to be visualized with 'outcomes' in the Column field, 'Date Created Conversation" in the Rows field, and 'count of outcomes' in the Values field. It was important to include "Parent Category" as a filter so that we can focus solely on 'theather' since that is the category that Louise's play corresponds to. 

Lastly, to visualize the data I needed to create a chart. Due to fact that I wanted to show how the values changed each month, a line chart was the logical choice. (Pictured below)

![alt text](https://github.com/willenny/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png?raw=true)

This line chart shows the month with the most successful fundraising campaigns is May. If 'Subcategory' were to also be included as a Filter and 'plays' was selected, May would still be the most successful month. Based on this, it is possible that Louise's play may have been successful if she had began the fundraising campaign in May. 

### Analysis of Outcomes Based on Goals

Using my Excel skills, I was able to visualize the percentage of successful, failed, and canceled plays based on the funding goal amount. An important new function, COUNTIFS(), will be used to collect the outcome and goal data for the “plays” subcategory. 

In the KickStarter sheet, I created a new sheet labeled "Outcomes Based on Goals." In the new sheet, I created the following columns to hold the data: 
Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled. 
In the “Goal” column, the following dollar-amount ranges were created so projects could be grouped based on their goal amount: 
Less than 1000, 1000 to 4999, 5000 to 9999, 10000 to 14999, 15000 to 19999, 20000 to 24999, 25000 to 29999, 30000 to 34999, 35000 to 39999, 40000 to 44999, 45000 to 49999, and 50000 or More

Using the new COUNTIFS() function, I populated the "Number Successful," "Number Failed," and "Number Canceled" columns by filtering through the Kickstarter "outcome" column, on the "goal" amount column using the goal ranges created, and on the "Subcategory" column using "plays" as the criteria.

E.g. for the Goal of 1000 to 4999 the number of successful projects was counted using the following code:
`=COUNTIFS(Kickstarter!D:D,">=1000",Kickstarter!D:D,"<4999", Kickstarter!F:F,"successful", Kickstarter!R:R, "plays")`

COUNTIFS works in the following way: 
1. Designate what sheet and cells you are searching through. `Kickstarter!D:D`
2. While looking through Column D (goal), only consider the project if the Goal is between $1000 (inclusive) and $4999. `Kickstarter!D:D,">=1000",Kickstarter!D:D,"<4999"`
3. Next search through Column F (outcome) and only consider the project if it was successful. `Kickstarter!F:F,"successful"`
4. Lastly, search through Column R (Subcategory) and only consider the project if it was a play. `Kickstarter!R:R, "plays"`
5. The COUNTIFS functions counts all of the project that meet these three criteria. 

I used the SUM() function to populate the "Total Projects" column with the number of successful, failed, and canceled projects for each row.
Next I calculated the percentage of successful, failed, and canceled projects for each row using the following code: `=ROUND(B2/E2*100,0` where the B Column represented the Number Successful and the E Column represented the Total Projects, giving the Percentage Successful in Column F. 

Lastly, I create a line chart titled "Outcomes Based on Goal" to visualize the relationship between the goal-amount ranges on the x-axis and the percentage of successful, failed, or canceled projects on the y-axis. To do this I assigned 'goals" in the Rows field, and 'Sum of Percentage Successful', 'Sum of Percentage Failed', and 'Sum of Percentage Canceled' in the Values field, which automatically generated " Summation of Values" into the Column field. (Pictured below) 

![alt text](https://github.com/willenny/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png?raw=true)

The line shows that projects that had fundraising goals less than $4999 were successful over 70% of the time. The only other time projects had a success percentage this high was when the fundraising goals was between $35000 to $44999. This would suggest that Louise may have set too high of a fundraising goal, which caused her not to reach her goal. 

Due to the percentage of canceled being 0% for each goal range, another helpful chart would be a segmented bar chart. (Pictured below)

![alt text](https://github.com/willenny/kickstarter-analysis/blob/main/Outcomes_vs_Goals_Segmented_BarChart.png?raw=true)

For each goal range, you can directly see the percentage comparison between successes and failures by observation at what percentage the bars are segmented.  

### Challenges and Difficulties Encountered

I was very excited to complete my first project and truthfully did not encounter many issues as I moved through the project. I made sure to refer back to my notes freqeuntly and use online resources to research any additional questions I had. The one problem that did take me a while to figure out was how to sort the goal ranges in my Outcomes vs Goals line chart. Because they were not simply all numbers ("Less than 1000" and "50000 or more"), Sort A to Z and Sort Z to A didn't work. I saw More Sort Options and then the option to sort Manual, which was promising! But the directions of "you can drag items to rearrange them" was vague. After about 30 minutes of trying to click and drag **everything**, then reading multiple online blog posts, then watching several videos, I finally figured it out. It was painful but satisfying in the end. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. Fundraising campaigns that began in May had the highest amount of successes. 
2. Fundraising campaigns that began in December had the lowest amount of successes. 

- What can you conclude about the Outcomes based on Goals?

Projects that had fundraising campaign goals of less than $5000 were the most successful. Conversely, projects that had fundraising campaign goals of $45000 or greater were the least successful. I think it's obvious that the lower your goal is, the more achieveable it is; but also to set realistic goals for your project. 

- What are some limitations of this dataset?

Some limitations to this dataset are... (come back to this).

- What are some other possible tables and/or graphs that we could create?

As I showed in the Outcomes based on Goals section, I also included a segmented bar chart to visually show and compare the percentage of successful and failed plays, due to the canceled being 0% for each month. 
