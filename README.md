# Best-Gym-Location

**Problem**

My friend Adam is passionate about fitness and wants to venture into the fitness industry by opening a gym or fitness center. However, he faces a challenge in determining the optimal location within a bustling city that can attract a broad audience and generate substantial profits. To assist him in this endeavor, I've decided to use my data science expertise to identify the ideal location.

I have sourced the latest demographic data  of the city from publicly avaiable website - Link below
https://open.toronto.ca/dataset/neighbourhood-profiles/
the dataset has varied number of features. For my analysis, I have acquired total population, age 15-45 population, no. of educated people, no. of employed people  as per the neighbourhoods they live in.
Leveraged **Google's Geocoding API** to get the geographical coordinates of each neighbourhood in the city. To study the current venues(happening places in the city) and existing gyms, I have used **Foursquare API** to get the number of venues and number of gyms in each neighbourhood.

Given the nature of our data-seeking patterns within unlabeled information - our study falls into the realm of unsupervised learning. To group similar neighbourhoods based on the extracted features, we've employed the K-means clustering algorithm. To determine the ideal number of clusters, we've applied both the elbow method and the Silhouette score, ultimately categorizing the neighbourhoods into three distinct clusters.

**K-means clustering model** has grouped neighbourhood into 3 clusters
cluster 1 : grouped less populated neighbourhoods with less no. of venues
cluster 2 : grouped neighbourhoods with large no. of venues
cluster 3 : grouped highly populated neighbourhoods

<img width="606" alt="image" src="https://github.com/PHANINDRA25/Best-Gym-Location/assets/136892334/8b3108c1-7e26-431f-8279-98bf590844a9">


As number of gyms are proportional to number of venues, lets pick an ideal location from cluster 2 with decent no. of gyms. As high population is also a major criteria , lets pick a location from cluster 3 which is among highly populated areas with less no. of gyms and with good number of venues

Cluster 2 has high no. of venues. 'High Park-Swansea' has the highest population in this cluster with highest no. of veneus=98 with 8 gyms. 'Rosedale-Moore Park' has comparable population with High park with 95 veneus but only 4 gyms. Hence from this cluster 'Rosedale-Moore Park' is the preferred choice

k means grouped 3 rd cluster neighbourhoods with high population and medium no. of venues . here 'West Humber-Clairville' has the highest population with 3 gyms and 28 venues and 'Wexford/Maryvale' has somewhat less popualtion taht west humber but has 46 venues with only 1 gym. Considering these factors, Wexford/Maryvale could be a best probable location from this cluster

Our final picks :

cluster 2 - Rosedale-Moore Park Popln - 20K no. of gyms -4 no. of venues 95 - most happening place

cluster 3 - Wexford/Maryvale Popln - 28K no. of gyms -1 no. of venues 46

If we run ratio analysis

Rosedale-Moore Park 20K/(4*95)=0.052

Wexford/Maryvale 28K/(1*46)=0.6

## Hence to open a gym Wexford/Maryvale would be the ideal location.

We need to consider other factors like land price, construction cost, local taxes and take decision based on that between the two neighbourhoods

