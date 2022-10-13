# DATA 512 Homework 2: Considering Bias in Data

## Goal
The goal of this assignment is to try to identify bias by investigating Wikipedia articles written about political figures from different countries. We will also be exploring the coverage and quality of the articles per country and seeing how these features could introduce bias. 

## Research Implications
Before going into the assignment, I expected that articles from countries that have lower literacy rates would not have as much access to peer reviewers, thus the articles from these countries would have fewer scores that will skew the quality score to seem high quality. I also expected that smaller countries would have less articles in general and this would also skew the total articles per capita to make it seem like smaller countries have higher coverage. Another point I noticed is that we are primarily looking at the English Wikipedia articles, so articles published about non-native English speaking countires may have a lower score because the article may not be well written or within the standards of the English-speaking Wikipedia community. Some surprising elements that I encountered while doing this assignment were that there some politicians associated with different countries and that the dataset is rather dynamic so much so that 2-3 Wikipedia articles have been deleted in the week we've been working on this assignment.    

Based on my results, it seems like English Wikipedia may not be a reliable resource for those who are interested in articles about non-native English speaking countries or smaller countries that are less known or less literate in general. This data source seems to be most reliable for those articles who may have peer reviewers who have access to English information and can fact-check the articles written on Wikipedia and make edits where they see fit. Since the data source is constantly changing, this means that the article quality can also constantly change, so in this aspect, the data source may not be reliable.    

A way researchers can normalize this dataset is to look into countries that all have English as a commonly spoken language and also have around the same number of politicians, similar population size, and similar literacy rate. By doing this, the ORES system would be able to make more accurate generalizations rather than producing biased scores for countries that may be more marginalized. 


## About the Data
  
We use two different data sources ```poli_clean.csv``` and ```pop_by_country.csv```.

The politician dataset was obtained through a data crawl on the following website: https://en.wikipedia.org/wiki/Category:Politicians_by_nationality.    
This dataset consists of the article name, Wikipedia url, and country of the politician.   
   
The population dataset is drawn from the https://www.prb.org/international/indicator/population/table/ published by the Population Reference Bureau.  
This dataset consists of the regions and countries in the Georgraphy column and the population (millions) of each region. The Geography column contains some rows that provide cumulative regional population counts. These rows are distinguished by having ALL CAPS values in the 'geography' field (e.g. AFRICA, OCEANIA). 

APIs used:   

ORES: https://www.mediawiki.org/wiki/ORES   
Machine learning tool that provides article quality score predictions.   

Info: https://www.mediawiki.org/wiki/API:Info   
Used the retrieve article metadata specifically the revision id.

Some noteworthy considerations:   
-There were some countries that have a population of 0 and these countries were filtered during the analysis step.   
-There are some duplicate values in the politicians dataset and only the rows that have the same name, url, and country were filtered out.   
-We only consider the regions that are lowest in hierarchy (i.e. North Africa rather than Africa).  

Wikimedia API: https://www.mediawiki.org/wiki/REST_API   
Content retrieved from the API is licesnsed under the CC-BY-SA 3.0 and GFDL licenses.   
Terms and Conditions of use: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions   

## Output Files
 -We created ```wp_countries-no_match.txt``` to display which countries did not match between the politician dataset and the population dataset.    
 -We created a csv that contains our variables of interest (country, region, population, article_title, revision_id, and article_quality): ```wp_politicians_by_country.csv```. This is the csv that we do our analysis with.

## Project Structure
```
└── data-512-homework_2
    ├── LICENSE
    ├── README.md
    ├── raw_data
    │   ├── pop_by_country.csv
    │   └── poli_clean.csv
    ├── outputs
    │   ├── wp_countries-no_match.txt
    │   └── wp_politicians_by_country.csv
    └── src
        ├──setup_and_analysis.ipynb
```
