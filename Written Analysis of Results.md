# Kickstarting with Excel

## Overview of Project

### Purpose
By using Excel and its functions, we are able to help Louise compare how different her fundraising campaign was to other similar campaigns. Our main focus was to determine how her play 'Fever' fared in relation to launch dates and funding goals. Using visuals to present the data, we are now able to give analysis to Louise about her play.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

Using my knowledge of pivot tables and graphing in Excel, I visualized campaign outcomes of successful, failed, and canceled, based on their launch date. The launch date refers to the month that the fundraising campaign began. Due to originally only being given the launch date as a Unix timestamp, it was essential to convert this into a more easily read date. `=(((J2/60)/60)/24)+DATE(1970,1,1)`

Next, I created a pivot table from the KickStarter worksheet, and placed the it in a new sheet, labeled "Theater Outcomes by Launch Date." When organizing the pivot table, the data is best going to be visualized with 'outcomes' in the Coloumn field and 'Date Created Conversation" in the Rows field. It was important to include "Parent Category" as a filter so that we can focus solely on 'theather' since that is the category that Louise's play corresponds to. 

Filter the pivot table based on "Parent Category" and "Years."
Place the appropriate pivot table fields in the columns, rows, and values.
Filter the column labels to show only "successful," "failed," and "canceled."



### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
