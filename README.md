# Segmenting and Clustering Neighborhoods in Toronto.
Applied Data Science Capstone/ IBM/ Coursera
# Report
## Introduction
### This report can help those who are planning to start a new business such as a Handicraft  shop in Toronto, Canada and need to find the best location for the shop.

## Background

Toronto is the most populous city in Canada. It is diverse and is the financial capital of the country. It is multicultural. It provides lot of business opportunities and business friendly environment. It has attracted many different players into the market. It is a global hub of business and commerce. The city is a major center for banking and finance, retailing, world trade, transportation, tourism, real estate, new media, traditional media, advertising, legal services, accountancy, insurance, theater, fashion, and the arts in Canada.
This also means that the market is highly competitive. As it is highly developed city so cost of doing business is also one of the highest. Thus, any new business venture or expansion needs to be analysed carefully. The insights derived from analysis can give good understanding of the business environment which help in strategically targeting the market. This will help in reduction of risk. And the Return on Investment will be reasonable.
 
Selecting the right location for a business is one of the first and very important decisions in running a business. Starting a new business in a metropolitan city such as Toronto can be challenging. Toronto has 140 neighborhoods with various places that attract tourists and people to visit. Neighborhoods of Toronto are different in terms of different factors that can directly affect the success chance of business. It is important to evaluate different neighborhoods based on the factors that are important for running a successful business such as the number of competitors and the potential demand in that neighborhood. 

## Business Problem
This project  trying to help to find the best neighborhood in Toronto to open a Handicraft shop. The challenge is to find a suitable neighborhood which is close enough to some amenities and venues, has fewer competitors.  A Handicraft shop is good to be near a place,  many people visit such as park, garden, cafe shop, playground, shopping center and so on. Also, a neighborhood that has fewer competitors is less risky for starting a new business. In this project attempt to rank the neighborhoods by consideration the amenities around and the number of competitors.



## Data


It will be using the below datasets for analysing Toronto city.

1. https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M,  the information about Post Code of the neighborhoods of Toronto.
2. http://cocl.us/Geospatial_data, the geographical coordinates of each postal code.
3. Foursquare API location data.


## Methodology

1. Get the information about Post Code of the neighborhoods of Toronto from wikipage: https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M,
2. Use BeautifulSoup for clean information and some standard features like .drop, .groupby, .replace for dataframe formation.
3. .read_csv  from http://cocl.us/Geospatial_data to get the latitude and longitude values of the neighborhoods of Toronto.
4. Use geopy library to get the latitude and longitude values of Toronto. The geographical coordinates of Toronto are 43.653963 , -79.387207.
5. Create map of Toronto using latitude and longitude values used .folium and add markers to map by .CircleMarker features.
6. Create URL by Foursquare API
7. Create a function to get all venues for each neighborhood and create a dataframe of them.
8. Group the venues across all neighborhoods of toronto by .groupby and .count features.
9. Count number of uniques categories and create a list of them by .len, .unique, .sort_values, .groupby and .count.
10. Create a file with dummy values by venue category (.get_dummies).
11. .Drop some venues categories from the data, witch irrelevant ('Airport', 'Rental Car Location', 'Bike Shop', 'Gay Bar', 'Strip Club', 'Nightclub', 'Electronics Store', 'Airport Food Court', 'Airport Gate', 'Airport Lounge', 'Airport Service', 'Airport Terminal')
12. Add column Total in dataframe (.sum features).
13. Determine the optimal value of K for our dataset using the Silhouette Coefficient Method. n_clusters=2 has highest Silhouette Coefficient. This means that 2 should be the optimal number of clusters.
For n_clusters=2, The Silhouette Coefficient is 0.7895622910021808.
14. Run k-means to cluster the neighborhood into 2 clusters. The Total and Total Sum of cluster 0 has smallest value. It shows that the market is not saturated.
15. Create Dataframe with Neighborhood,Cluster No and Total Sum.
16. Create Clusters Map with .folium.
17. Identify categories of potential competitors .loc and check each using data .foursquare.
18. Using .Marker mark competitors' positions on the map.
19. Import statistics library and count the coordinates of the center of the area defined by clustering (.mean).
 20. Build the Map with .folium and with .CircleMarker mark the area most advantageous for opening a store.


## Results

From this venues data it was filtered and used only study relevant data. During the study, the area of the most favorable store location was determined, taking into account the location of competitors.


## Discussion

When choosing a place to open a store, it is worth remembering the location of competitor stores. You should also pay attention to the area marked on the map with red circles. During the clustering, it was found that the saturation of the market with various venues is higher, therefore, their consideration should be excluded.


## Conclusion
After the completion of this project, we have a small example of what real research projects look like. I used some commonly used python libraries to collect web data, used the Foursquare API to explore areas of Toronto, and saw the results of area segmentation using the Folium map flyer. The potential for such an analysis in a real business problem is discussed in great detail. Finally, since my analysis was mainly focused on the possibilities of opening a customer-oriented needlework store, regardless of social factors, the model turned out to be simple and clear. For other types of business, of course, you should complicate the model and introduce more criteria for analysis. Hopefully this type of analysis will provide you with an initial guide to more real-world data science challenges.
 






