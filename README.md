# Taxi-service-performance-analysis
Power BI | SQL | Google sheets

## Metrocar performance analysis

### Project Background
Metrocar is a ride-hailing platform (similar to Uber/Bolt), which allows users to download an app, register, request a ride, complete the trip, make payment, and leave a review.
Objective of Management: To explore why a significant number of users do not complete their first trip, optimize user experience, and improve conversion rates at every stage of the process.
Task: To conduct a comprehensive analysis of the user funnel to determine where and why users drop off and to propose specific actions for product improvement, marketing optimization, and customer experience enhancement.
Key Available Data:
- App downloads, including platform and user age group;
- New user registrations linked to download sessions;
- All ride-related events: from request to completion or cancellation;
- Transactions, including payment amounts and statuses;
- User reviews, including texts and ratings.

### Business Questions Analysis
#### User Funnel
##### Observations:
- 26.4% of users who downloaded the app completed and paid for at least 1 ride. 
- Largest losses of users on different steps of the funnel:
	- signed up: 
		- 25.35% loss out of downloads (74.65% of users signed up after the download);
	- ride requested: 
		- 47.45% loss out of downloads (52.55% of all users who downloaded the app requested at least 1 ride)
		- 29.6% loss out of sign ups (70.4% of users went further after sign up);
	- ride completed: 
		- 73.6% loss out of downloads (26.4% of all users who downloaded the app completed at least 1 ride) 
		- 49.23% loss out of rides accepted (50.77% of users went further after sign up);
	- ride reviewed: 
		- 81.58% loss out of downloads (18.42% of all users who downloaded the app reviewed at least 1 ride)
		- 30.24% loss out of rides paid (69.76% of users went further after ride reviewed).

   
#### Drop-off Points
##### Observations:
- 55.16% of the requested rides were completed and paid for. 
- Largest losses on different steps of the funnel:
	- ride accepted:
		- 35.57% cancellations out of rides requested (64.43% of rides were accepted); 
	- ride completed: 
		- 41.98% cancellations out of rides requested including 35.57% after ride request (hereinafter - not_accepted/cancelled) and 6.41% after ride request and acceptance (hereinafter - accepted/cancelled). 
		- 9.96% cancellations out of rides accepted (90.04% of accepted rides were completed)
	- ride paid: 
		- We noticed that the number of rides paid is lower than the number of the rides completed for 11,024 rides (4.93%), this variance should be investigated in more detail to ensure that the payment was collected;
	- ride reviewed: 
		- 26.53% of rides paid were not reviewed (73.47% of rides paid were reviewed).





- We had a closer look at ride cancellations, which affected the ‘ride accepted’ and ‘ride completed’ Rides Funnel stages. 
	- General analysis


Out of 385k requested rides:
224k rides (58%) were completed
162k rides (42%) were cancelled, including 137k (36%) not_accepted/cancelled and 25k (6%) accepted/cancelled.

	If we analyse the chart above and the Users Funnel simultaneously, we can assume that the 25k of accepted/cancelled rides resulted in approximately 6k users (25.6% of downloads) not transferred from ‘ride accepted’ to ‘ride completed’ step of the funnel. These users were lost after first cancellation after acceptance.

	- Distribution of cancellations on a monthly, daily, hourly basis
		- Rides cancelled/rides requested ratio has been steadily decreasing monthly, from 94% cancellations in January 2021, to 27% cancellations in January 2022 and 4% cancellations in March 2022. 





		- Rides cancellations were evenly distributed across weekdays with around 23k cancellations on each day of the week.



		- Rides cancellations dynamics during the hours of the day were in line with ride requests and seem reasonable considering rush hours.




	- Distribution of cancellations based on the waiting time
		- Not_accepted/cancelled rides: The cancellations were made within a range of 2-20 minutes after the ride request. The average waiting time was 11.03 minutes. The number of cancelled rides was almost evenly distributed across the waiting time. 


		- Accepted/cancelled: The cancellations were made within a range of 2-10 minutes after the ride acceptance. The average waiting time was 5.96 minutes. The number of cancelled rides was also almost evenly distributed across the waiting time.




#### Platform Efficiency Analysis
##### Observations:
- The most revenue generating platform was ios - 60.84% revenue. Other platforms generated 29.25%, web generated 9.91%.


- The number of users who completed a ride and the number of rides completed were distributed across platforms with the same structure as revenue.




- According to the charts below there are no platforms that have conversion rates significantly lower than others. 
	- 26.4% of all users completed and paid for at least 1 ride. Web had the lowest conversion rate - 25.6%, ios had the highest - 26.5%.


	- 55.2% of all rides were completed and paid for. Web had the lowest conversion rate - 54.6%, android had the highest - 55.4%.



    
#### Age Group Analysis
##### Observations:
- The biggest portion of revenue was generated by the age groups of 35-44 - 29.88%. 
The second place by revenue was attributed to an Unknown age group - 29.47%. Other categories accounted for: 10.87% (18-24), 19.72% (25-34), 10.15% (45-54) of revenue.


- The number of users who completed a ride and the number of rides completed were distributed across age groups with the same structure as revenue.





- With respect to conversion, the Unknown category includes both users who did not sign up and those who did not specify their age.  
26.4% of all users completed and paid for at least 1 ride. Conversion rate across those users who specified their age was quite similar, the highest was attributed to age groups 18-24 and 35-44 - 35.9%, the lowest to 45-54 - 34.5%.

55.2% of all rides were completed and paid for. 45-54 age group had the lowest conversion rate - 54.3%, 18-24 had the highest - 56.4%.




#### Other observations - Rating
##### Observations:
- Based on the analysis of the rides ratings provided by the users, we identified that: 29.74% of the rides were rated at ‘1’, which is the lowest rating. About 50% of rides were rated at ‘4’ and ‘5’ (25.33% and 25.13% respectively). Other categories amounted to 20% of the rides together.


- Average rating by driver amounted to 3.08. We identified that the average ride rating for the majority of drivers was in a bucket of ‘>3 and <=4’: 47.06%. Second biggest bucket was ‘>2 and <=3’: 44.95%. Other buckets amounted to about 8% together.





### Recommendations
Based on the analysis performed we compiled a list of recommendations to consider.

##### General
We observed a significant decrease in revenue starting from January 2022, herewith the quantity of rides requested has decreased in a similar manner, price per ride being stable throughout the whole period of analysis. 
Further actions should be taken as to identify the potential causes of such decrease. We suggest to initially focus on any major changes in the Company’s policies and procedures introduced starting from 2022 and any external changes (eg. new players on the market, legislation etc.), followed by deeper analysis, if needed.





##### Users Funnel
We suggest to perform an additional analysis and further decide on the action plan:
- signed up: 
	- review the user experience during the sign up procedure, identify the potential drawbacks (eg. time consuming or inconvenient sign up)
	- review the current marketing initiatives for sign up (eg. bonuses or discount on sign up)
- ride requested:
	- review the user experience during the ride request, identify potential inconveniences
	- review the requests from the users to the tech support, summarise the main issues
	- ensure that the quantity of available drivers is consistent with the quantity of passengers during the day (including rush hours)
	- review pricing, benchmark to the main competitors	
- ride completed: (see Cancellations below)
- ride reviewed:
	- review the user experience during the rating and review procedure, identify the potential drawbacks
	- review the current marketing initiatives for rating and consider update

##### Rides Funnel
With respect to the rides completed but seemingly not paid for, identify the substance of the issue, review the payment process, introduce safeguards against such situations in the future (if needed).
see Cancellations below.

##### Cancellations
A separate analysis needed for not_accepted/cancelled and accepted/cancelled rides is needed, separately initiated by drivers and users. The main issues leading to cancellation should be investigated.
- Analyse (if available) or introduce reviews from users/drivers upon cancellation.
- Identify the most common concerns (eg. waiting time until acceptance, distance to driver, long time upon the drivers arrival etc.) and plan the next steps accordingly.
- Benchmark the key metrics to the main competitors (eg. waiting time until acceptance, drivers time of arrival etc).

##### Platforms
- The biggest platform in all respects is ios (revenue, number of users, number of rides). It also has the highest conversion rate by users and second highest by number of rides. However, the difference in conversion across the platforms is rather insignificant. If the plan is to boost the largest platform, the budget should be channelled to ios.
- Other platforms as it was mentioned above have similar conversion rates. Some of the budget can be channelled to these platforms.

##### Age groups
- We noticed that the second place by revenue was attributed to an Unknown age group - 29.47%. An additional investigation into the matter is required to understand the reasons behind users not providing information on their age and what can be done to decrease the % of users in the Unknown category.
- The most significant age group of users is currently 35-44. An marketing analysis would be beneficial on how to target other groups.


### Annex 1. Dashboard
