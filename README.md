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

The Advanced Filter dialogue is shown below.

![AdvancedFilter](/resources/AdvancedFilter.png)

Then the pivot table was filtered on by category for 'theater' and column labels sorted descending (or Z to A) and filtered for 'not including "live"'.

![PivotTableColumnsFiltered](/resources/PivotTableColumnsFiltered.PNG)


### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](/resources/Outcomes_vs_Goals.png)

To create the above graph, it was necessary to count the number of successful, failed and canceled kickstarters with respects to the subcategory 'plays'. This was done using the `COUNTIFS()` function with criteria based on the goal field separated by goal brackets, starting with goals from zero to 999, 1000 to 4999, 5000 to 9999, and so on until greater than 50000. A summation of the counts by goal brackets was then performed. Finally, to provide a sense of scale, the counts are respectively divided by the summation to provide percentage successful, percentage failed and percentage cancelled. On the graph itself, the x-axis uses the goal brackets while the data series are the fields 'Percentage Successful', 'Percentage Failed', and 'Percentage Canceled'. As depicted below.

![ChartSelectData](/resources/ChartSelectData.png)

### Challenges and Difficulties Encountered

There were no difficulties encountered to producing the above visualizations. Potential difficulties could have been missing the request to examine a distinct sub category. Additionally, potential errors could have included mis-typing and incorrect formula generation. Inputting the formula for each cell (B1:H13) would be tedious and can be prone to error. As a results, my solution was to use excel's `CONCATENATE()` function and it's short cut (`&`) in the formula and setting conditions in other cells (that could later be hidden) and unique entry filtered lists from 'Kickstarter' sheet. 

Hard coded formula:

![HardCodedFormula](/resources/HardCodedFormula.PNG)

Variable solution formula:

![ImprovedFormula](/resources/ImprovedFormula.PNG)

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

One conclusion that can be drawn based on the data is that *theater* ventures are most often launched in May. Secondarily, based on the distance between the successful point height to a super imposed failed and canceled point, it can be suggested that ventures launched in May also have the highest success rate. This is confirmed by actual calculation taking the count of successful outcomes divided by the total of outcomes in the given month as shown by the screen capture below. 

![Success_rate_of_theater_vs_launch_month](/resources/Success_rate_of_theater_vs_launch_month.png)

One issue with this presented data is that is does not specify the sub category of plays and results may therefore be slightly skewed or inaccurate.

- What can you conclude about the Outcomes based on Goals?

It can be implied based on the graphed information that there is typically higher probability of successful funding the lower the goal is however also spikes to higher probability of success for funding projects with a goal of 35000 to 44999. The other conclusion that may be drawn is that *with zero 'percent canceled'*, having both percentage successful and percentage failed graphed together does not provide any value added information because they are complimentary to reach 100% and using either of 'Percentage Successful' or 'Percentage Failed' provides the same information; just in an optimistic or pessimistic perspective based on tracking success or failure. 

- What are some limitations of this dataset?

Based on raw data alone, some of

- What are some other possible tables and/or graphs that we could create?

As touched on in drawing conclusions about the 'Outcomes based on Launch Date', an additional filter to add to the pivot table would be to specify 'plays'. Adding the filter 'Subcategory' with respects to 'plays' provides us with a new revelation: that June is the highest success rate for launching kickstarters, as sampled below.

![Success_rate_of_plays_vs_launch_month](/resources/Success_rate_of_plays_vs_launch_month.png)

Additionally, presenting success and failure with respects to both goal and time elapsed (between date created and date ended) can provide additional insight. For instance, a high goal with a short elapsed time presents the suggestion to start one's Kickstarter before funds are critically needed to allow for exposure time and donation. 

Another series of data that could be examined in tables or charts could be based on region or 'country'. A pivot table by countries for rows for instance can provide insight on interest and success rate by the size of a stacked bar graph (example depicted below). However, being that Kickstarter is a American corporation, it's likely that this data shows bias towards American projects.

![PlayOutcomesByCountry](/resources/PlayOutcomesByCountry.png)
