# -Amazon_Vine_Analysis
Big Data analysis using Google Colab, Pyspark, Postgres/pgAdmin, AWS RDS

Overview
I analyzed Amazon reviews produced by members of the Amazon Vine program.  This is a service that allows reviews of their products and determine if there are any biases between Vine members and Non-Vine member's reviews.

To determine if there is any bias towards favorable reviews from Vine members vs. non-members.  Part of the process is to identify the percentage of 5 star ratings to total rating. As part of this exercise, we were asked to choose from datasets to extract, transform and load into a dataframe in order to complete our analysis. To perform the analysis, I used:

PySpark to extract the dataset, transform the data, connect to AWS RDS instance and load the transformed data into pgAdmin.
Google Colaboratory to import PySpark libraries and connect to Postgres in order to create SQL tables and export the results.

Results
The data was filtered by:

Count of Total Votes equal or greater than 20.
Percent of Helpful Votes to Total Votes equal or greater than 50%.
![PercentVotes](https://user-images.githubusercontent.com/108476566/203383077-2fe80f05-68dd-4bfb-9ab5-b9dc4cdb93cd.png)


The results reduced the total number of reviews from 3M to 50.7K. This allowed us to answer the following questions:

1. How many Vine reviews and non-Vine reviews were there?

Vine members made up only 2.1% (1,080) of the reviews whereas the remaining 97.9% were Non-Vine members (49,659).
VineNonVineTotal

vine

nonVine

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

Vine members gave 454 out of 1,080 reviews a 5 star rating.
Non-Vine members gave 23,034 out of 49,659 reviews a 5 star rating.
3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

42% of the reviews for Vine members were rated 5 stars.
46.4% of the reviews for Non-Vine members were rated 5 stars.
Summary
Based on the results, Vine members did not show bias when rating their products considering that the number of 5-star ratings was about 10% less than Non-Vine members (42% vs. 46.4%). With this, we can assume that Vine customers are more critical when submitting their review. However, in order to support this assumption further, we should include all of the data rather than filtering it to a percentage of helpful vs. total votes as we did for this analysis. Reviewing the data as is would give us more information and allow us to further support our assumption as shown below.

nonfilteredtotal

In addition, running the same analysis using datasets from different product categories can provide us with the whole picture of whether reviews made by Vine members are bias.
