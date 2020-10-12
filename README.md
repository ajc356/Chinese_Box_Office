# Film Success in China 

**Motivation**

More Chinese are flocking to theaters than ever before. In the past twenty years the Chinese box office grew from \$1 billion USD in annual sales to nearly [\$10 billion USD](https://chinapower.csis.org/chinese-films/#easy-footnote-bottom-2-4228). 



In February 2019, the director of China’s National Film Bureau, called on China to become a “strong film power” on par with the US by 2035. 
He outlined revenue targets for China to annually produce 100 movies that would each earn more than \$15 million. Yet in 2019 only [46 Chinese films](http://epaper.ynet.com/html/2020-01/02/content_346077.htm?div=-1) earned more than \$15 million. 

In this project, I propose that before China can fulfill its ambitions to become a “strong film power”, it is necessary to take a closer look at what’s going on in the domestic Chinese market. Therefore the question that I have set out to investigate is: What explains the success of films in the Chinese market?

**Guiding Question** 

What explains the success of films in the Chinese market?

**Methods** 

To begin my analysis, I first had to determine the population of films released in the Chinese market. To do this I used Beautiful Soup to scrape the [Box Office Mojo](https://www.boxofficemojo.com/weekend/by-year/2019/?area=CN) website for films released in China for all complete available years which included 2016-2019. 

This gave me a list of 1086 titles with complete entries – however the extent of data Box Office Mojo offers for each title is somewhat limited,  so from here I turned to a preexisting [Kaggle IMDB dataset](https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset?select=IMDb+movies.csv) to see if I could glean some additional features. 

**Model** 

After experimenting with several different models I ended up dropping a number of the genre features and limiting my analysis to:  
•	USA gross revenue  
•	Released only in China  
•	Chinese production  
•	Runtime  
•	Length of Release Period  
•	Genres:  
o	Action, Adventure, Animation,  Comedy, Crime, Documentary, Drama, Fantasy, Thriller

And again, my target is Chinese gross revenue.

**Results** 

Again after experimenting with a number of different models, I ultimately found Lasso to be the best – although Lasso and regular linear regression scored very similarly (nearly identical r-squared), when I ran k-fold cross validation, Lasso ultimately produced a marginally better r-squared such that my model is able to explain 31% of the variation observed in the data. 

**Conclusions/Implications** 

We see a really interesting paradox in the data:

The strongest indicator of a film’s success in China was ultimately whether or not it was released only in China (with no intl distribution) and this is highly correlated with negative film performance – ie if a film is only released in China it is unlikely to generate much revenue. Yet at the same time, if a film is a Chinese production that is strongly and positively correlated with a film performing well

As for which genres bring the most money these include : Animation, Fantasy, Action.   
While the worst performing genres include: Documentary, Drama. 

**Future Work** 

This project was a first cut at understanding the Chinese film market, however there’s additional work that could be done going forward

In addition to continuing to improve my model by making optimal use of existing data, we would be able to gain even better insights by working with more and better data because so many films are missing IMDB data about key things like budget, current features are limited. One avenue that would be really exciting to explore would be Chinese sources of data as I am not confident that either BoxOfficeMojo or IMDB have a comprehensive account of the full population of Chinese films. 
Additionally another promising area for future research would be to dig into the success of Chinese films in international markets – something that will no doubt become more important as China continues to chart its course to becoming a strong film power on par with the US
