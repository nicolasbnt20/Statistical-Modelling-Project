# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
This Project is about the integration and analysis of data collected from multiple APIs, focusing on the CityBikes network. The goal was to retrieve and combine data from external sources such as bike slots, nearby points of interest, and other characteristics linked to the points of interest, in order to discover potential relationships between the variables.The project aimed to evaluate these relationships and model them with a regression model, hoping to gain insights.

## Process
### API Connection : CityBikes
I started the project by connecting to the CityBikes API to retrieve real-time data on bike stations in the city I chose: Paris. The reponse was parsed and transformed into a usable DataFrame, which was the foundation for the following steps.
### API Connection : Foursquare and YELP
I used the stations coordinates from the CityBikes DataFrame to collect informations about nearby points of interest with both the Foursquare and YELP APIs. I then compared the quality of the results and chose to proceed with the YELP data as it provided larger quantity of data, a better average number of points of interest by station, less missing data, and ratings which were not available in the Foursquare API.
### Data Merging
I then merged the data obtained from YELP with the original data concerning CityBikes. This new DataFrame would be the base of my analysis. I did a second round of EDA to better understand the data and get rid of potential errors left.
### Model Building
Finally, I constructed a regression model to test potential relationships between several variables. I personally chose the total number of bikes slots, and the number of points of interest / the average ratings of these places as the variable to build my model around. I then evaluated and interpreted the results. 

## Results
The regression model revealed a very weak relationship between the selected independent variables and the dependent variable. Despite filtering beforehand, the model showed a poor fit with a very low Adj.R Squared value. Also the high p-values suggested that the chosen variables were not statistically significant. 

## Challenges 
One of the first challenges was selecting meaningful features from the Foursquare and YELP APis without overwhelming the dataset. I also an unexpected issue during the EDA where many of my POIs were located outside the set radius, despite filtering the parameters. It required getting rid of a significant amount of data collected to avoid skewing the results. I ran into some formatting difficulties when importing and working with SQLite3. Lastly, interpreting the very poor results of the model led me to question the viability of the chosen variables for prediction.

## Future Goals
With more time, I would have expanded the range of variables pulled from the YELP API to enrich the dataset and potentially improve the regression model. I would also have structured the SQLite3 portion better by dividing the table into two normalized ones with bike stations on one side and POI-related informations on the other. Lastly I would have standardized or normalized the data / data distribution before modeling and run further tests after evaluation to see if I could achieve better results.
