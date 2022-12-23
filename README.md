**Statistical guideline for a financially successful movie taking inflation into consideration**


**Abstract :**

Movies are a universal source of entertainment that bring us joy no matter how we're feeling. But have you ever thought about the huge profits some movies make? And what factors contribute to their financial success?

The movie industry plays a significant role in the entertainment market, with the global box office worth $42.2 billion in 2019. But what makes a movie financially profitable? Is it the length of the film, the presence and fame of certain actors, the genre, or the budget?

To find out, we're using a data-driven approach to analyze a subset of movies released in the US from 1980 to 2010. We'll measure success using the profit feature, which is calculated as the difference between the revenue and budget. We'll also gather additional data points from Wikidata, TMDb, and Imdb to get the revenue, budget, and ratings. Let's see what we can discover about the factors that drive movie profitability!


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






