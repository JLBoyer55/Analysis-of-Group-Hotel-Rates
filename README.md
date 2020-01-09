# Analysis of Hotel Room Rates
## Motivation
I work for a company that has built an online platform for meeting planners to source and book hotels for group travel based on specified criteria.  In general, hotels market to two types of customers:

•	Leisure travelers consist of individuals or groups of fewer than 10 people who typically book rooms on a short-term basis

•	Group travelers consist of 10 more people who book farther in advance

Unlike leisure, group rooms cannot be booked online, and there is limited visibility into pricing for group rooms.  Hotel pricing is dynamic due to the perishable inventory, and hotels use yield management strategies to optimize rate and occupancy.  There is no central platform for buyers and sellers to exchange information on pricing, availability and buying criteria.  My company is addressing the booking inefficiencies by automating the search process with software.  I wanted to analyze pricing patterns for group rates and answer the following questions: 

	How can you assess value when comparing room rates for different destinations?  
	How do rates vary by region over time?  
	Is there a relationship between group and leisure room rates?
  

## Data  
To answer these questions, I used daily room rate pricing data from 2018 for 58 U.S. regions.  This data was purchased from a third party and provided to me by my company.  I aggregated the data by month and region to analyze patterns for the year.  

## Analytical Approach
To answer the question of value, I aggregated the daily pricing data by month and region and calculated each region’s group and leisure rate.  I then ranked each region by the group rate for each month and categorized them into four tiers:  Tier 1 contained the 14 highest group rates, Tier 2 the next 14, and so forth.  For each tier, I calculated the Tier rate to use as a benchmark, which was the aggregated rate for all regions in that tier.  It was then possible to assign an index score for each region:  a score above 100 means a region’s rate is higher than the benchmark tier rate, while a score of less than 100 means the region is pricing under the benchmark rate.  

The benchmark rate provides context to rates and gives an idea of fair market value.  For example, if a meeting planner is evaluating rates for California destinations for a company conference, it would be useful to know that the rate for San Francisco has an index score of 150 and the rate for San Diego has an index score of 110.  The index tells the meeting planner that the company will have to pay a premium over the benchmark rate to hold the conference in San Francisco.  
 
The charts in the dashboard are designed to make either the months or the region the fixed variable.  In certain cases, a traveler has a fixed destination and needs to see where the best value can be obtained throughout the year.  In other situations, the dates of travel cannot be changed, but different destinations can be selected based on rate and value.  I also wanted to see how rates varied by region over time and if certain “luxury” locations such as San Francisco and New York ever offered good value to a traveler. 
Lastly, I wanted to see if there is a relationship between group and leisure rates.  Because groups typically book farther in advance and reserve 10 or more rooms, I expected group rates to be lower than leisure rates.  I calculated the ratio of group rates to leisure rates and created a visualization to highlight any regions in which the group ratio exceeded 100.  I also calculated the correlation between group and leisure rates by month and region.  There is a strong correlation for each month, but there were seven regions in which the correlation was below .70. 
 
Although group rates typically are below the leisure rate as expected, it became evident that certain marquee events can cause the leisure rate to spike above the leisure rate.  The data showed one such spike in January in San Francisco, and I discovered that there were three major industry conferences in January 2018.  If an organization understands the value of its business to a region, it can use that data to negotiate more forcefully to secure favorable pricing and amenities.  Regions can also use this information to determine which events are worth bringing to their area to drive demand. 

## Tools Used
•	Excel – data was provided as 12 separate workbooks

•	Pandas - for exploration and aggregation of the data

•	PowerBI - for creating dashboards
