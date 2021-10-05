# Amazon_Vine_Analysis

## Overview of the Analysis

The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products.We will need to pick one of the Amazon datasets and use PySpark to
 perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we’ll use PySpark, Pandas, or SQL
 to determine if there is any bias toward favorable reviews from Vine members in your dataset.Also we'll write a summary of the analysis to submit to the SellBy stakeholders. 

## Methodology

This study provides a comparison of paid (Vine) and non-paid reviews, looking to see if paids draw a higher percentage of 5-start reviews than non-paid results.

## Setting up the study

I stored the data for this study on Amazon Web Services, and linked this to a postgres instance on my laptop. I used PySpark in a google collab environment to extract, transform and load 
the data to the database.

## Results

### Deliverable 1:
 
-An Amazon Review dataset is extracted as a DataFrame
-The extracted dataset is transformed into four DataFrames with the correct columns

customer_table Dataframe:

![d1.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/d1.PNG?raw=true)

products_table Dataframe

![d1-2.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/d1-2.PNG?raw=true)

review_id_table Dataframe

![d1-3.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/d1-3.PNG?raw=true)

vine_table Dataframe

![d1-4.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/d1-4.PNG?raw=true)

-All four DataFrames are loaded into their respective tables in pgAdmin

![customers.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/customers.PNG?raw=true)

![product_table.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/product_table.PNG?raw=true)

![review_id_table.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/review_id_table.PNG?raw=true)

![vine_table.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/vine_table.PNG?raw=true)

### Deliverable 2 :

-The DataFrame for the vine_table is created using PySpark.

![D2-1.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-1.PNG?raw=true)

-The data is filtered to create a DataFrame where there are 20 or more total votes 

![D2-2.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-2.PNG?raw=true)

-The data is filtered to create a DataFrame where the percentage of helpful_votes is equal to or greater than 50% 

![D2-3.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-3.PNG?raw=true)

The data is filtered to create a DataFrame where there is a Vine review 

![D2-4.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-4.PNG?raw=true)

The data is filtered to create a DataFrame where there isn’t a Vine review

![D2-5.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-5.PNG?raw=true)

The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews 

![d2-6.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/d2-6.PNG?raw=true)

![D2-7.PNG](https://github.com/Praveeja-Sasidharan-Suni/Amazon_Vine_Analysis/blob/main/Images/D2-7.PNG?raw=true)


### Deliverable 3 :
A written Analysis is submitted:

* Participating in the Vine program does not appear to yield more 5-start ratings. We see that 32% of Vine products receive a five star ratings, which is less than 
* the 52% of non-Vine products achieving this rating.

* The numbers of Vine reviews in this set is too small to draw solid conclusions, and the product class (watches) might not draw a good sample of Amazon consumers - watches are subject to prestige buying, either to show success (e.g. rolex) or to show athletic ambitions (e.g. ironman watches) as more and more people forgo watches and use their phones to see the time.

* The Vine program may be more heavily used by new vendors trying to attract attention and break into the market. It would be interesting to compare multiple products from the     same manufacturer to get better comparability between the Vine and non-Vine products.
