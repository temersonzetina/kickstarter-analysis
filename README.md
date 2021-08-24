# kickstarter-analysis
Analysis and visuals of data about kickstarter campaigns by sector/field

# Kickstarting with Excel

## Overview of Project
The purpose of this analysis was to visualize potential correlations between key variables relating to time and fundraising amounts within the Kickstarter dataset. Each record in this dataset includes quantitative and qualitative information about individual fundraising campaigns. The variables of interest include a given campaign’s fundraising goals, outcomes, and launch date. Insights from this analysis are meant to inform the client about whether fundraising success may be correlated with (1) month of launch date and (2) the goal (by amount of currency) set at the beginning of the campaign.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
The question guiding this analysis was: “What is the relationship between launch month (between the years of 2009-2017) and fundraising outcome for campaigns in the ‘theater’ category?” To complete this analysis, I began by adding a “Years” column in the Kickstarter worksheet. This involved applying the YEARS formula to the "Date Ended Conversion" column. Once included in the pivot table, this new “Years” column would enable the user to select certain years of interest and observe variation between years while viewing campaign success data.

Next, I created a pivot table to compile information about the variables of interest, labeling it “Theater Outcomes by Launch Date.” I added the filters “Parent Category” (which would allow me to filter for ‘theater’) and “Year” (which allows the user to alternate between clusters of years as needed). To focus the analysis on “month,” I changed the row label units to “Month.” Under rows, I added “Date Created Conversion,” which is the variable that describes day, month, and year of a campaign’s launch date. Under columns, I added the variable “Outcomes,” which conveys how many “failed,” “canceled,” or “successful” outcomes were achieved in a given timeframe. I then created a pivot chart, titling it “Theater Outcomes Based on Launch Date.” This chart visualizes a line graph for each of the 3 outcome types, showing how theater campaigns fared based on month (between the years of 2009 and 2017). The pivot was filtered to include all years when the chart was made, but users may select different year combinations to observe variation in the data.

### Analysis of Outcomes Based on Goals
The question guiding this analysis was: “What is the relationship between each play campaign’s fundraising outcome (in terms of success, failure, or cancelation) and its original fundraising goal?” To begin this analysis, I created a new sheet that would reflect the total number of successful, failed, and canceled campaigns (grouped in intervals) reflecting the campaign goal (each row was a new interval). For instance, the first interval would capture success data for campaigns with goals “Less than $1000.” The second interval described campaign success for those with goals from “$1000 to $4999”, and so on, until reaching the culminating interval of “More than $50,000.” In that same sheet, I added columns for “Total Projects,” “Percentage Successful,” “Percentage Failed,” and “Percentage Canceled” (which constituted columns 6-8).

I populated columns 2-4 (i.e. Number Successful, Number Failed, et al.) by using the COUNTIFS formula to count all of the records including a certain set of criteria (i.e. Successful plays whose goal was between 30000 and 34999, etc.). I populated the “Total Projects” column by using the SUM formula for each row’s data from columns 2-4. Then, to populate columns 6-8, I used simple division formulas between columns 2-4 and the “Total Projects” column. This yielded data reflecting percent successful, failed, and canceled by goal interval.

Once the table was complete, I was able to create a line chart detailing campaign outcomes based on goal interval. This chart allows the observer to surmise a potential relationship between goal (by interval) and campaign outcome.

### Challenges and Difficulties Encountered

The first task posed just one minor challenge, which was to change the row label units from “Years” (which was the default) to “Months” (which is the preferred unit based on the scope). I overcame this challenge by searching for advice on changing row label units on Google. This yielded the information that I needed.

The second task posed several challenges. The first related to the problem of figuring out how to arrange the COUNTIFs formula to include the precise set of criteria. I overcame this by checking Google for the correct syntax and altering my formula text until the results seemed correct. The second difficulty had to do with sorting the goal intervals in order on the graph. For some reason, Excel did not read the order correctly, which meant that the graph was incorrect. I fixed this problem by adding another column to the left of the goal interval column that ordered the intervals correctly. Then, when creating the pivot chart, I nested the goal intervals under the interval order variable. This ensured they were in the correct order.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
(1) Campaigns launched in and around May were by far the most successful. Conversely, campaigns launched around the turn of the calendar year were the least successful. Between 2009 and 2017, there were nearly 5 times as many successful campaigns begun in May (166) than in December (37).
(2) Though the total number of campaigns launched each month varied greatly, the total number of failed campaigns hovered close to 50. If time of year were a strong, independent predictor of success, we would have expected to see the number of failed campaigns mirror more closely the line graph of successful campaigns. This means there may be more layers to uncover before concluding what the top predictors of success are.

- What can you conclude about the Outcomes based on Goals?
(1) Campaigns with goals under $5000 were somewhat or very likely to be successful.
(2) The odds of success change rapidly as goals increase above $5000, after which success rates plummet. Just around 20% of campaigns with goals between $25-30K were funded.
(3) However, the correlation seemed not to be linear, as a greater percentage of campaigns with goals around $40K were successful than unsuccessful. 
(4) When including the entire dataset, campaign goals are only a moderate predictor of outcomes. However, when you isolate certain intervals – for instance, $0 to $20K, and $20K to $40K – the data demonstrated stronger predictability. Users of this data should avoid extrapolating outside of pre-determined intervals, or will need to perform certain transformations to achieve linearity.

- What are some limitations of this dataset?
It would have been helpful to know each campaign’s minimum launch amount. It’s reasonable to assume that some donors may take this information into account before making a decision to fund. This information would help them to address the question of “how realistic is it that this project gets off the ground?” This is a common consideration among investors. It’s possible that some investors, if they weren’t furnished with this information by the campaign lead, estimated a floor for a given campaign to get off the ground. Investors don't want to invest in something that has a very low probability of even piloting, let alone becoming effective or profitable.

Similarly, investors are commonly interested in knowing the past fundraising history of donors. A variable featuring information about each campaign lead’s total amount fundraised over a lifetime may be relevant. Savvy investors – especially those with the most money to invest - often do this research on their own as a means to assess a given fundraiser’s abilities.

One could argue that investors of Kickstarter campaigns don't fall into the category of investor I'm referencing. However, some likely will, and those are probably the most experienced (and well-endowed) donors. This would make them a prime stakeholder group for whom to design.

- What are some other possible tables and/or graphs that we could create?
Simply because a campaign was not “successful” in the categorical sense does not mean it was a complete failure. As Column O in Kickstarter demonstrates, a large number of campaigns were very close (80% or better) to goal before ending the campaign. Whether the campaign leads ultimately determined their campaign to be a “success” or “failure” may not match up with the outcome formally ascribed to them based simply on whether they achieved their original goal. You could imagine, for instance, that a lead who raised above 90% to goal may consider themselves more successful than not, and may still move forward with the project. With that in mind, a graph with percent funded by outcome may be a more useful visual for tracking the relationship between goal and a campaign’s ultimate “success.”

In terms of time, which appeared to be an important construct in this analysis, it may also be interesting to consider duration of campaign as opposed to simply month of launch date. An additional graph that plots duration (in days) on outcome would signal whether there may be a correlation between how long a campaign remained active and whether it reached its goal. Replacing “outcome” with “percent funded” may yield similarly useful results.
