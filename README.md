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
The resulting CityBikes dataframe and ......... dataframe were joined together and validated. The data was then explored through data visualization to start the process of understanding the relationships
Refer to: notebooks > joining_data.ipynb
 
### 4. Statistical Model

Refer to: notebooks > model_building.ipynb

## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

## Challenges 
(discuss challenges you faced in the project)

## Future Goals
(what would you do if you had more time?)
