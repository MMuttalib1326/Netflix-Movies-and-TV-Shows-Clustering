<h1 align="center"> Netflix Movies and TV Shows Clustering</h1>


![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

![image](https://cdn.arstechnica.net/wp-content/uploads/2022/07/netflix.jpg)
<p align="center"> 
<img src="image/netflix-logo.gif" alt="..." height="150px">
</p>

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Index

| Sl. No. | Section         |  
|:--------|:-------------------------|
|    1    |  Introduction  </a>    | 
|    2    |  EDA Summary    </a>   | 
|    3    |  Clustering Summary  </a> | 
|    4    |  Content Based Recommender System </a> |
| 5 |   Conclusions  </a> |

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 1. Introduction:
* Netflix, headquartered in California, is a popular subscription streaming service and production firm. According to Statista, Netflix had approximately 220.67 million paid subscribers worldwide as of the second quarter of 2022. It is crucial that they effectively cluster the shows that are hosted on their platform in order to enhance the user experience for its subscribers.
* We will be able to understand the shows that are similar to and different from one another by creating clusters, which may be leveraged to offer the consumers personalized show suggestions depending on their preferences.
* The goal of this project is to classify/group the Netflix shows into certain clusters such that the shows within a cluster are similar to each other and the shows in different clusters are dissimilar to each other.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 2. EDA Summary:
* There are more movies (69.14%) than TV shows (30.86%) in the dataset.
* Raul Campos and Jan Suter together have directed 18 movies / TV shows, higher than anyone.
* The highest number of movies / TV shows were based out of the US, followed by India and UK. The top 3 countries together account for about 56% of all movies and TV shows in the dataset. This value increases to about 78% for top ten countries.
* Netflix has greater number of new movies / TV shows than the old ones.
* The dramas is the most popular genre followed by comedies and documentaries. These three genres account for about 41% of all movies and TV shows. This value increases to about 82% for top 10 genres.
* On average a greater number of shows are added in the months of October, November, December, and January.
* There is a decrease in the number of shows added in the year 2020, which might be attributed to the covid-19-induced lockdowns, which halted the creation of shows. We have Netflix data only up to 16th January 2021, hence there are less movies added in this year.
* The majority of the shows on Netflix are catered to the needs of adult and young adult population.
* Over the years, Netflix has consistently focused on adding more shows in its platform. Though there was a decrease in the number of movies added in 2020, this pattern did not exist in the number of TV shows added in the same year. This might signal that Netflix is increasingly concentrating on introducing more TV series to its platform rather than movies.
* The TV series in the dataset have up to 16 seasons, however the bulk of them only have one. This might mean that the majority of TV shows has only recently begun, and that further seasons are on the way. There are very few TV shows that have more than 8 seasons.
* The length of a movie may range from 3 min to 312 minutes, and is almost normally distributed.
* Netflix has several movies on its site, including those that were released in way back 1942. Movies produced in the 1940s had a fairly short duration on average. On average, movies made in the 1960s have the longest movie length. The average length of a movie has been continuously decreasing since the 2000s.
* Dramas, comedies, and documentaries are the most popular genre for the movies on Netflix. International, crime, and kids are the most popular genre for TV shows on Netflix.
* Raul Campos and Jan Suter have together directed in 18 movies, higher than anyone yet. This is followed by Marcus Roboy, Jay Karas, and Cathy Gracia-Molina. Alastair Fothergill has directed three TV shows, the most of any director. Only six directors have directed more than one television show.
* Samuel West has appeared in 10 movies, followed by Jeff Dunham with 7 movies. David Attenborough has appeared in 13 TV shows, followed by Michela Luci, Jamie Watson, Anna Claire Bartlam, Dante Zee, Eric Peterson with 4 TV shows.

 
## 3. Clustering Summary:
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
* Clusters were built on the attributes: Director, Cast, Country, Rating, Listed in (genres), Description
* Steps involved in preprosessing:Tokenize the corpus, Remove non-ascii characters, Convert all words to lowercase, Remove punctuation marks, Replace all numbers with its respective textual representation, Stemming and Lemmatization
* Text corpus was vectorized using TFIDF vectorizer, and 20000 attributes were generated.
* More than 80% of the variance is explained just by 4000 components. Hence to handle the curse of dimensionality, only the top 4000 components were taken, which will still be able to capture more than 80% of variance in the data.

### 3.1. K Means Clustering:
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
* The optimal number of clusters were built after visualizing the elbow curve and the Silhouette score.
* Highest Silhouette score is obtained for 6 clusters using k-means clustering. Hence, the number of clusters for k-means clustering was taken as 6.
* Silhouette score at 6 clusters: 0.0082

### 3.2. Hierarchical Clustering:
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
*  Clusters were built using the Agglomerative clustering algorithm, and the optimal number of clusters were built after visualizing the dendogram.
* From the dendogram, at an Euclidean distance of 3.8 units, 12 clusters can be built. Hence the number of clusters were taken as 12.
* Algorithm: Agglomerative clustering
* Distance: Euclidean
* Linkage: Ward

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 4. Content Based Recommender system using Cosine Similarity:
![image](https://projex.gumlet.io/content-based-recommender-systems-project/images/Content-based_Filtering_Recommendation_System_Machine_Learning.png?w=320&dpr=2.6)
* We can build a simple content based recommender system based on the similarity of the shows.
* If a person has watched a show on Netflix, the recommender system must be able to recommend a list of similar shows that s/he likes. To get the similarity score of the shows, we can use cosine similarity.
* The similarity between two vectors (A and B) is calculated by taking the dot product of the two vectors and dividing it by the magnitude. We can simply say that the CS score of two vectors increases as the angle between them decreases.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 5. Conclusions:
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
* In this project, we worked on a text clustering problem wherein we had to classify/group the Netflix shows into certain clusters such that the shows within a cluster are similar to each other and the shows in different clusters are dissimilar to each other.
* The dataset contained about 7787 records, and 11 attributes.
* It was found that Netflix hosts more movies than TV shows on its platform, and the total number of shows added on Netflix is growing exponentially. Also, majority of the shows were produced in the United States, and the majority of the shows on Netflix were created for adults and young adults age group.
* It was decided to cluster the data based on the attributes: director, cast, country, genre, and description. The values in these attributes were pre-processed, tokenized, and then vectorized using TFIDF vectorizer. Through TFIDF Vectorization, we created a total of 20000 attributes.
* Principal Component Analysis (PCA) was used to handle the curse of dimensionality. 4000 components were able to capture more than 80% of variance, and hence, the number of components were restricted to 4000.
* We first built clusters using the k-means clustering algorithm, and the optimal number of clusters came out to be 6. This was obtained through the elbow method and Silhouette score analysis.
* Hierarchical clustering model was built using the Agglomerative clustering algorithm, and the optimal number of clusters came out to be 12. This was obtained after visualizing the dendogram.
* A content based recommender system was built using the similarity matrix obtained after using cosine similarity. This recommender system will make 10 recommendations to the user based on the type of show they watched.

![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
![--](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


