# The Battle of Neighborhoods: Best neighborhood with more chinese restaurant in manhattan

## Introduction
The purpose of this Project is to help people in exploring better facilities around their neighborhood. It will help people making smart and efficient decision on exploring great neighborhood out of numbers of other neighborhoods in Mahattan, New Tork.

Lots of Chinese people are migrating to various states of US and Chinese food are becoming now more and more populars nowadays. This project is for those people who is explorting Mahattan and are interedted in finding more Chinese restaurants. 





## The Location:
Manhattan , known regionally as the City, and the urban core of the New York metropolitan area, is the most densely populated and smallest of the five boroughs of New York City, and coextensive with New York County, one of the original counties of the U.S. state of New York. Manhattan serves as the city's economic and administrative center, cultural identifier, and historical birthplace. 

## Foursquare API:
This project would use Four-square API as its prime data gathering source as it has a database of millions of places, especially their places API which provides the ability to perform location search, location sharing and details about a business.


## Work Flow:
Using credentials of Foursquare API features of near-by places of the neighborhoods would be mined. Due to http request limitations the number of places per neighborhood parameter would reasonably be set to 100 and the radius parameter would be set to 700.

## Clustering Approach:
To compare the similarities of two cities, we decided to explore neighborhoods, segment them, and group them into clusters to find similar neighborhoods in a big city like New York and Toronto. To be able to do that, we need to cluster data which is a form of unsupervised machine learning: k-means clustering algorithm
Libraries Which are Used to Develope the Project:

Pandas: For creating and manipulating dataframes.

Folium: Python visualization library would be used to visualize the neighborhoods cluster distribution of using interactive leaflet map.

Scikit Learn: For importing k-means clustering.

JSON: Library to handle JSON files.

XML: To separate data from presentation and XML stores data in plain text format.

Geocoder: To retrieve Location Data.

Beautiful Soup and Requests: To scrap and library to handle http requests.

Matplotlib: Python Plotting Module.


# Data desciption

##Data Link:  
https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/labs/newyork_data.json

We will use New York dataset which we scrapped on Week 3. Dataset consisting of latitude and longitude, zip codes.

## Foursquare API Data:

We will need data about different venues in different neighborhoods of that specific borough. In order to gain that information we will use "Foursquare" locational information. Foursquare is a location data provider with information about all manner of venues and events within an area of interest. Such information includes venue names, locations, menus and even photos. As such, the foursquare location platform will be used as the sole data source since all the stated required information can be obtained through the API.
After finding the list of neighborhoods, we then connect to the Foursquare API to gather information about venues inside each and every neighborhood. For each neighborhood, we have chosen the radius to be 100 meter.
The data retrieved from Foursquare contained information of venues within a specified distance of the longitude and latitude of the postcodes. The information obtained per venue as follows:
1. Neighborhood
2. Neighborhood Latitude
3. Neighborhood Longitude
4. Venue
5. Name of the venue e.g. the name of a store or restaurant
6. Venue Latitude
7. Venue Longitude
8. Venue Category

##Extracting the data

I first read data through JSON file and create a datafram, then got Latitude and Longitude data of these neighborhoods via  Geocoder package. Finally I used Foursquare API to get venue data related to these neighborhoods.

![Neighborhoods of Manhattan](https://github.com/andyzengmath/Coursera_Capstone/blob/main/manhattan-neighborhood.png)

## Methodology

First, I need to get the list of neighborhoods in Manhattan, New York. I extracted relative information from the JSON data and did standard data preprocessing and cleaning. Then I put them into a Pandas dataframe, and use Geocoder to retrieve coordinates.

Next, using Foursquare API, I pulled the names, categories, latitude, and longitude of the venues. With this data, I couldcheck how many unique categories that I can get from these venues. Then, I analyzed each neighborhood by grouping the rows by neighborhood and taking the mean on the frequency of occurrence of each venue category. This is to prepare clustering to be done later.

Finally, I focused specifically on “Chinese restaurants”. I used the k-means clustering. K-means clustering algorithm identifies k number of centroids, and then allocates every data point to the nearest cluster while keeping the centroids as small as possible. It is one of the simplest and popular unsupervised machine learning algorithms and it is highly suited for this project as well. I have clustered the neighborhoods in Manhattan into 3 clusters based on their frequency of occurrence for “Chinese food”. Based on the results (the concentration of clusters), I will be able to recommend the ideal location to explore the restaurant.

## Result

- cluster 0 (blue): less Chinese restaurant
- cluster 1 (red): medium
- cluster 2 (green): more Chinese restaurant

![K-means clustering](https://github.com/andyzengmath/Coursera_Capstone/blob/main/cluster.png)

The neighborhood with Chinese restaurants are in cluster 2 which is Chinatown. Two other neighborhoods close to Chinatown, little Italy and Lower East Side, are in cluster 1 which also have more Chinese restaurants.

There is another center with more Chinese restaurants, which consists of 5 neighborhoods: Mahattan Valley, Morningside Heights, Manhattanville, Hamilton Heights, and Central Harlem.

Hence I recommend there two centers for exploring Chinese restaurant, and Chinatown is the first place to check out.

