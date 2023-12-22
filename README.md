# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of this project is draw regression model conclusions on the relationship between the number of bikes in a particular location compared to point of interests. Specifically, we will be trying to find relationship between empty Bicing(bike share company in Barcelona, Spain) bike stop spots (ie. bike is in use) and the proximity to "museums". The term "museums" was chosen to denote venues that served an important role in being cultural hubs and thus should attract more visits by individuals. In understanding this data, it may help model how individuals are travelling around the city - especially to hotspots such as these museums that usually attract a lot of foot traffic. 

## Process
### 1. Query CityBikes API
With the queried data, it was formed into a dataframe. The process of EDA ensured that the resulting dataframe was ready for step 4.
Refer to: notebooks > city_bikes.ipynb

### 2. Query Foursquare API and Yelp API
With the two sets of queried data, they were qualitatively compared to each other. Foursquare data was chosen over Yelp as it proved to include more data points and include data about venues that were not strickly "museums". The Foursquare API included venues that were on great significance including landmarks, cathedrals and other high foot-traffic and cultural hubs. Though Yelp included a lot of data that was more specific such as ratings, transactions, phone numbers and countless others, they were not quite as useful for this research question. The main metrics needed were the proximity to the bike stops and the number of venues close by each bike stop.
Refer to: notebooks > yelp_foursquare_EDA.ipynb


### 3. Joining Data
The resulting CityBikes dataframe and Foursquare dataframe were joined together and validated. The data was then explored through data visualization to start the process of understanding the relationships.
Refer to: notebooks > joining_data.ipynb
 
### 4. Statistical Model
A linear regression model was run asking the question, how much could the number of venues near a given bike stop estimate the percent of bikes being used from the bike stop.
Refer to: notebooks > model_building.ipynb

## Results
Comparing the Yelp API and Foursquare API, the Yelp API returned results with a much more in depth amount of information than that of the Foursquare API. However, while using the Foursquare API and using 'query=museums', it actually returned a more robust and varied quantity / quality of venues. Since my research question is based more about the presence of these venues, I ultimately decided to use Foursquare since the extra information from Yelp would not be useful. 

When running a single linear regression model between the variables of 'venues_nearby' and '% used' (bikes), we were able to conclude that there was a statistic significant result and that the null hypothesis was rejected. With a r-squqred value of 0.678, 67.8% of the variation could be explain by this model. The percent of bikes being used at a given bike stop had a linear positive relationship to the independant variable of number of venues nearby (radius of 200 meters) [coefficient of 0.1863]. This result was statistically significant with a p-value of 0.000 (much less than the accepted p<0.05).

## Challenges 
One of my major limitations were the number of API requests I could send. Because of my inexperience with the process, there were many instances were I had to resend requests due to improper formatting, accidental requests or even forgetting to save the results to a .json file and restarting the kernal. This ultimately led to me being unable to request restaurant data and I had to suffice with my 'museum' data. However, I was still able to run regression models with the data, analyze the results and question project questions such as ranking based on ratings. I also found difficulty in normalizing the data. Again, due to inexperience, I spend a large amount of time funbling around with the nested lists and dictionaries trying to make sense of how they fit within each other (and consequently, how to format my dataframe normalization codes).

## Future Goals
This project's scope was such an interesting view into how large scale projects could be pursued. The limitation of API request (even without my lack of experience) would potentially be quickly used up if this was a large scale project to track a company's success and future business decisions. In the context of my Barcelona based company 'Bicing', a future goal and direct application of this project would be to gather the API requests of CityBikes throughout the hours of the day (say, once per hour) over a span of days or even weeks. Yelp and Foursquare API requests can be made for all commercial destinations and be combined to give the most complete picture of all available venues. With deleting duplicates in venue per bike stop and congregating the hourly CityBikes data, Bicing would have the opportunity to answer many other pressing questions such as:
Do we regularily run out of bikes at a certain location or region and how much should we expand these areas?
Where are the most visited areas and should we look into better advertisment in that area?
How does the cycling mode of transportation compare with other common types of transportation like vehicles or public transit? How may we aim towards conversions - especially for shorter commutes that bikes could successfully and easily integrate into?
