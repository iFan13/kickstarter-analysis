# Kickstarting with Excel

## Overview of Project

The purpose of this analysis is to provide Louise with easily digestable information.

### Purpose

Louise's play *Fever* came close to it's fundraising goal in a short amountof time. She wants to understand how different campaigns fared in relation to their launch dates and their funding goals. This analysis will provide visual representations of various campaign's statistics with respects to relevant categories to Louise's project in question (that is: her theater play *Fever*). Source data for this analysis is also included [here](/Kickstarter_Challenge.zip)


## Analysis and Challenges


### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](/resources/Theater_Outcomes_vs_Launch.png)

To create the above chart, a pivot table was created from the 'Kickstarter' worksheet and applying the following fields to the pivot report areas respectively.

* Parent Category and Years (a created field by using the `YEAR()` function with the argument of the Date Created Conversion field) in the Filters
* outcomes in the Columns
* outcomes in the Values
* Date Created Conversion in Rows

![PivotTableFields](/resources/PivotTableFields.PNG)

Then the pivot table was filtered on by category for 'theater' and column labels sorted descending (or Z to A) and filtered for 'not including "live"'.

![PivotTableColumnsFiltered](/resources/PivotTableColumnsFiltered.PNG)


### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](/resources/Outcomes_vs_Goals.png)


### Challenges and Difficulties Encountered

There were no difficulties encountered to producing the above visualizations. Potential difficulties could have been missing the request to examine a distinct sub category. Additionally, potential errors could have included mis-typing and incorrect formula generation. Inputting the formula for each cell (B1:H13) would be tedious and can be prone to error. As a results, my solution was to use excel's `CONCATENATE()` function and it's short cut (`&`) in the formula and setting conditions in other cells (that could later be hidden) and unique entry filtered lists from 'Kickstarter' sheet. 

Hard coded formula:

![HardCodedFormula](/resources/HardCodedFormula.PNG)

Variable solution formula:

![ImprovedFormula](/resources/ImprovedFormula.PNG)

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

A conclusion that can be drawn based on the data is that *theater* ventures are most often launched in May. Further to that, based on the distance between the successful point height to a super imposed failed and canceled point, it can be suggested that ventures launched in May also have the highest success rate. This is confirmed by actual calculation taking the count of successful outcomes divided by the total of outcomes in the given month as shown by the screen capture below.

![Success_rate_of_theater_vs_launch_month](/resources/Success_rate_of_theater_vs_launch_month.png)


- What can you conclude about the Outcomes based on Goals?

It can be concluded that 

- What are some limitations of this dataset?


- What are some other possible tables and/or graphs that we could create?

Additional tables or graphs that can be created 
