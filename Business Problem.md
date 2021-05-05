# Business Problem: The Battle of Neighborhoods

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
