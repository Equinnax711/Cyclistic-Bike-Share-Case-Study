# Cyclistic-Bike-Share-Case-Study

#### Problem Statement
Cyclistic, a successful bike-share company, launched in 2016, slowly expanding across Chicago and gaining revenue. Within Cyclistic’s business model, there are various pricing plans that customers can choose to purchase. 

The single-ride pass, full-day pass, and annual membership. Based on Cyclistic’s finance analysts, customers that purchase the annual membership are much more profitable than those that choose the single and full day passes. Therefore, in order for Cyclistic to generate more revenue and further grow, Cyclistic must figure out how to convert those casual riders to annual riders. This can be done by analyzing the differences between the current casual and annual riders. Looking at this data will allow Cyclistic to make an informed decision on how to maximize revenue in the near future.

#### Data Security & Organization
The data is located on Cyclistic’s historical trip data website, from which we can download the data file. It is organized in an excel csv format, with data columns for unique ride-ids, type of bike ridden, ride-start and ride end time, start location names and ids, end-locations names and ids, starting and ending latitude and longitude numbers, and member status. There are no issues with credibility within this dataset because no rides have been omitted from the data. It represents the census of cyclistic rides, removing the chance of sampling bias or the chance that the dataset is not representative of the entire population. 

Because this data has been made publicly available under the LLC data license agreement, we are able to use it without penalty or accessibility concerns. Data such as personal identification and credit card numbers have not been included within this dataset in order to protect and respect the rider’s right to privacy. 

To make sure that this dataset is ready for merging, cleaning, and analysis, we'll first have to ensure that all columns match up correctly. This includes renaming columns, rerouting data, dropping unneeded columns, and ensuring data types are consistent within each quarterly period to maintain an organized standard structure. Checking and revising this was the first priority. The four quarterly datasets were then merged into a complete dataset.

#### Data Cleaning & Transformation

After prepping and merging data, we'll move onto cleaning the dataset to make sure any unformatted, missing, or wrong data will be made consistent and clear in preparation for data transformation. New columns that are critical to the analysis of the dataset will be transformed from current columns using the "mutate" function. Changes to the merged dataset have been elaborated on below. 

Issue #1: Within the "member_casual" column, there seem to be four different labels: Subscriber, member, customer, and casual. Based on the given information within the case study, customers should be labeled as either a member or a casual. This will be solved by renaming all subscribers as members and all customers as casual.

Addition #1: The date and time stamps for this dataset are all combined into one character string and placed in either the "started_at" or "ended_at" columns. Splitting this data up into separate columns into time, day, month, and year will allow us to make more meaningful connections in our analysis.

Addition #2: Currently, there are columns that tell us the start_station id/name and the end_station id/name. This information is not quantifiable, meaning that we cannot utilize it in its raw state. To use it effectively, we will add a column called "ride_duration" that tells us how long it took to get from the start station to the end station.

After implementing the ride_duration column, I went back and checked if the durations were all positive using a quick sign-check function. Since the function did not output zero, it means that there are some zeros or negative ones within the sign check column. This means that we can conclude there are negative ride durations within the column, possibly due to Cyclistic taking the bikes out of service for maintenance. These all need to be removed and cleaned before continuing with the analysis.

#### Analysis

We'll be analyzing the two different member types by first calculating different statistics that they each have and creating visualizations based off of those results. These will allow us to better visualize the data given. Our first graph will compare the number of rides per day between each member type, our second one will compare the average duration of each ride per day between each member type, our third one will compare the number of rides per month between each member type, and our fourth graph will compare the number of rides per hour between each member type. 

![Graph #1](https://github.com/Equinnax711/Cyclistic-Bike-Share-Case-Study/blob/78ce669625978a1a23b0d30f4f1e5acfa375c554/Graphs/Bike%20Share%20Graph%20%231.jpg)

Graph #1 (Number of Rides per Day for each Member Type): This graph shows that the number of rides for cyclistic members increase during the weekdays and greatly drops off during the weekends. However, for casual members this is the opposite. The number of rides increases during the weekends and decreases during the weekdays. This is likely because casual members are using the cyclistic bikes for weekend fun and excursions in Chicago. During the weekdays, the casual customers have to return back to work and don't have free time to use their bikes to sight-see and travel around the city. For Cyclistic members, these people most likely use their bike to travel to and from their workplaces. This can be further analyzed by creating a visualization for frequency of bike rides against time among cyclistic members.

![Graph #2](https://github.com/Equinnax711/Cyclistic-Bike-Share-Case-Study/blob/8b21674175a38f0d30a1d1b6b15b5c5b9385286c/Graphs/Bike%20Share%20Graph%20%232.jpg)

Graph #2 (Average Duration of Rides per Day for each Member Type): Looking at the cyclistic members, the average duration is quite constant, with a slight increase on Sundays and Saturdays. The average duration for members is also much lower than the average duration for a casual member bike ride on all days. This provides further evidence towards cyclistic members using the bike service to go to and from their workplaces, as they travel the same distance every workday and only use the bike for that specific commute. Casual members have a much higher average duration across the entire week that vary from day to day. This provides evidence towards a more relaxed and longer bike ride, with them renting the bike for longer to go around the city to take in the views.

![Graph #3](https://github.com/Equinnax711/Cyclistic-Bike-Share-Case-Study/blob/8b21674175a38f0d30a1d1b6b15b5c5b9385286c/Graphs/Bike%20Share%20Graph%20%233.jpg)

Graph #3 (Number of Rides per Month for each Member Type): Looking at this graph, we can see that ride-share bike usage spikes during the summer months for both casual and member users. This is most likely due to the better weather outside, allowing them to get out and bike instead of staying indoors.

![Graph #4](https://github.com/Equinnax711/Cyclistic-Bike-Share-Case-Study/blob/8b21674175a38f0d30a1d1b6b15b5c5b9385286c/Graphs/Bike%20Share%20Graph%20%234.jpg)

Graph #4 (Number of Rides per Hour for each Member Type): Looking at the cyclistic members, we can see that the number of rides drastically spikes around 7 to 9 am and around 4 to 6 pm. This matches perfectly with the usual 8 hour workday cycle and tells us that a larger percentage of cyclistic members use the ride-share bikes to commute to work. For casual customers, the number of rides begins to ramp up from 7 am to 12 pm, slows down from 12 pm to 5 pm, and begins to drop back down at 5 pm. This graph confirms both our assumptions for why member usage spikes during the weekdays of the week and why casual usage spikes during the weekends.

#### Advice for Marketing Analysis team

Based upon our data analysis, we can say that the data points towards Cyclistic members utilizing the biking service for their commute to and from work. This is shown in the higher frequency of rides and a consistent average duration during the weekdays. Cyclistic casual customers most likely use the bike service in order to bike around the city for their own enjoyment, as shown by the increase of bike rides on the weekends and a more erratic pattern of average duration across the week.

Thus, our data analyst team advises to target the marketing campaign towards an eco-friendly type of advertisement, encouraging people that live within Chicago to bike to work using their bike-share instead of driving. This not only paints Cyclistic in a good light, but also targets our main audience quite well, as many of the people that are Cyclistic members commute using their bikes. Additionally, these advertisement campaigns should be placed on our bikes and released on social media during prime commuting hours in order to reach as many potential future members. 

In future analysis, more trends could be shown on a longer term basis. Data for when each of the members signed up for the membership and further analysis on monthly membership engagement/usage could be helpful towards our case study. It would allow us to decide the most optimal time to release the advertisement in Chicago.
