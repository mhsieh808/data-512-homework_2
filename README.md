# DATA 512 Homework 2: Considering Bias in Data

## Goal
The goal of this assignment is to try to identify bias by investigating Wikipedia articles written about political figures from different countries. We will also be exploring the coverage and quality of the articles per country and seeing how these features could introduce bias. 

## Research Implications



## About the Data
  
We use two different data sources ```poli_clean.csv``` and ```pop_by_country.csv```.

The politician dataset was obtained through a data crawl on the following website: https://en.wikipedia.org/wiki/Category:Politicians_by_nationality.    
   
The population dataset is drawn from the https://www.prb.org/international/indicator/population/table/ published by the Population Reference Bureau.  

Some noteworthy considerations:   
-There were some countries that have a population of 0 and these countries were filtered during the analysis step.   
-There are some duplicate values in the politicians dataset and only the rows that have the same name, url, and country were filtered out.   
-We only consider the regions that are lowest in hierarchy (i.e. North Africa rather than Africa).  

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
