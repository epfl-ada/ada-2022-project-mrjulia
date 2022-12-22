**Statistical guideline for a financially successful movie taking inflation into consideration**


**Abstract :**

Everyone loves movies! Whenever you are happy or sad, movies are one of the best companies for us. But when you are watching the movie, do you ever think of the astronomical profits that some movies make ? And maybe of the factors that make them financially successful?

Indeed, The movie industry plays an important role in the entertainment market size, as of 2019 the global box office was worth $42.2 billion.

Whether it is the duration of the Movie, the presence of certain actors and their notoriety, the genre it belongs to, or maybe the budget dedicated to the movie ? We aim to use a data

driven approach to reveal what makes a movie financially profitable.

For the purpose of our analysis, we will constraint our CMU Movies dataset to a subset of movies that were released in the US between 1980 to 2010.  We will be measuring the success using a Profit feature defined as the difference between the revenue and the budget, and we will enrich our CMU subset with scraped data points from Wikidata and TMDb to get the revenue and budget and with the Imdb dataset to get the ratings. 


**Research Questions:**

-Is it possible to find a trend or possibly a set of factors that contribute to the financial success of a US movie taking into account the inflation through time ?

-What is the relationship between **the Profit and the genre in this subset of movies**? What are the most common **intersections between genres** (most common pairings) ?

-Which topics and words in the **plot summaries** are correlated with blockbuster films? What is the general connotation of these words ? 

-Does the presence of certain notorious actors (award winning ) have an impact on this success ?

-What is the correlation between the budget for making a US movie and its financial success ?  



**Datasets:**

IMDB movies : can be found in https://www.imdb.com/interfaces/ website. It contains 
various data from titles to crews and directors who worked in a movie.
For now, we used this dataset to retreive average ratings and number of votes.
This would help us in our approach for weighted average rating.

Budget: We performed scraping for budget (alongside box office revenue) of movies over two sources, wikidata
and tmdb. For wikidata we scraped our data over movies from the United States
and selected only non zero results. The same approach was conducted on tmdb queries
over the movies at hand in the initial cmu dataset. This data will help us
to get a better grasp of the financial success based on profit.



**Main performed steps during milestone 2 :**



Step 1: General Pre-Processing :

As a first step of our preprocessing pipeline, we took a look at the CMU data corpus first provided and tried to do some preliminary cleaning : 

example : check all the movies that had missing freebase movie id and drop them. We do the same thing for actors that have missing freebase actor id. 

(further details in the preprocessing notebook)

Step 2 : Data augmentation :

As we said in the previous section, we tried to augment data using external datasets so that we can extract more information about movies and what makes them financially successful : we web scraped from wikiData and TMDb, movie budgets and their revenues since we assume that these types of variables are related to the financial success of a movie. We also augmented our movies with the ratings we got from IMDb datasets to see if the financial success is correlated with the perceived popularity that the movie got. 

Step 3 : Data wrangling and description:

We performed the descriptive steps of our data, namely looked for the distribution's features, and showed some correlations. We applied our constraints on the data and tried to make general comments.


**Proposed Methods:**

In depth correlation analysis :

Our goal would be to look in depth at the correlation we found using the  scipy.stats library and pearsonR function. The pearsonR function actually computes the correlation coefficient for every pair factor based on the dataset we provided and the p value to show the significance of the correlation. Finally, we would like to perform data visualization on the results obtained that would support our final report.

Actor awards analysis :

To measure the influence of actors we decided at first to measure their notoriety (specific to the movie industry) by web scraping the awards each actor won each year. We then group the total number of awards won by each actor of a given movie to try and find correlation between the financial success of a movie( movie box office revenue) and the casting choice. 

Summary plots analysis :

Our aim is to use the movie plot summaries in order to find a relationship or an insight leading us to the financial success of a movie. The problem is to try to identify which kind of plotline maximizes revenue (by performing a keyword analysis). 

In the provided jupyter notebook, we worked on one plot summary (Movie ID = 23890098) in order to familiarize ourselves with the plots dataset. We will apply the same ideas to all the summaries in future steps of the project. 

We analyze the keyword factor by using the word cloud visualization library (It is a visualization that can display a collection of words retrieved from text or document). We then try to do sentiment analysis to determine the general connotation behind the movie summary plot( positive, negative or neutral). We would like to enrich these connotations with more sentiments in future steps.

We started by using the positive-words.txt and negative-word.txt ( we want to enrich these word dictionaries furthermore ) that we used in previous homeworks in our provided example in the summary plot notebook. 

We then use the following formula to determine the degree of positivity Degree = (number(positive) - number(negative))/number(words) 

Combination of factors analysis 

In addition to the correlation between factors that we aim to do. We want to Investigate if  some combinations of factors can be a great indicator of financially successful  good movies. and perform We want to fit our data with both linear regression and  tree-based regression and compare between both these models. After discussion, we decided to learn more about the XGBoost model and how we can perform it on our dataset to understand its correlation more. 

Isolate the effect of the movie genre:

In order to isolate the effect of the movie genre on its revenue, we try to get rid of confounders. We had the idea to encode each movie using one hot encoding of its genres and then perform in depth correlation analysis to see if the presence of one genre might be important for the movie in order to achieve financial success. 

Clustering analysis of similarities between the movies:

We want to try the approach of clustering the movies that achieved the most profit and see if we can find a trend or a set of factors following which a movie is destined to be a financial success.

**Proposed timeline:**

*21-11-2022 to 27-12-2022:*

-project break due to the homework 

-assigning each one of us one of the following tasks 

*28-11-2022 to 4-12-2022:* 

In all these tasks, we assume that each teammate can add more features and scrape more points of needed from the datasets already provided

-apply all the example plot analysis provided on all the blockbuster movies we choose (teammate 1)

-performing clustering analysis : (teammate 2)

-analyze the effect of genres on the profit :(teammate 3)

-actor award analysis ( teammate 4)

*1-6 december :*

-perform the in-depth correlation analysis with interpretation of the result

5 december :

-start of the Milestone 3 






