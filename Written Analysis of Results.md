# Kickstarting with Excel

## Overview of Project

### Purpose
By using Excel and its functions, we are able to help Louise compare how different her fundraising campaign was to other similar campaigns. Our main focus was to determine how her play 'Fever' fared in relation to launch dates and funding goals. Using visuals to present the data, we are now able to give analysis to Louise about her play.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

Using my knowledge of pivot tables and graphing in Excel, I visualized campaign outcomes of successful, failed, and canceled, based on their launch date. The launch date refers to the month that the fundraising campaign began. Due to originally only being given the launch date as a Unix timestamp, it was essential to convert this into a more easily read date. The following code successfully converted the Unix timestamp in a readable date. `=(((J2/60)/60)/24)+DATE(1970,1,1)`

Next, I created a pivot table from the KickStarter worksheet, and placed it in a new sheet labeled "Theater Outcomes by Launch Date." When organizing the pivot table, the data is best going to be visualized with 'outcomes' in the Coloumn field, 'Date Created Conversation" in the Rows field, and 'count of outcomes' in the Values field. It was important to include "Parent Category" as a filter so that we can focus solely on 'theather' since that is the category that Louise's play corresponds to. 

Lastly, to visual the data I needed to create a chart. Due to fact that I wanted to show how a value changed each month, a line chart was the logical choice.

![alt text](https://github.com/willenny/kickstarter-analysis/blob/[branch]/Theater_Outcomes_vs_Launch.png?raw=true)

!(Theater_Outcomes_vs_Launch.png)



### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
