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


The data results reduced the total number of reviews from 3M to 50K. 

1. Vine reviews when compared to non-Vine reviews:

Vine members made up 2% (1,080) of the reviews versus the remaining 98% were Non-Vine members (49,659).
VineNonVineTotal
![VineNonVineTotal](https://user-images.githubusercontent.com/108476566/203383834-83c017f5-4bc9-45eb-b812-57fd5bf0b4eb.png)

![Vine](https://user-images.githubusercontent.com/108476566/203384279-d761524e-96f5-4475-bad3-d136447a16d2.png)

![NonVine](https://user-images.githubusercontent.com/108476566/203384386-7587033d-2d05-4005-bdd6-7e4d9c044895.png)

2. Vine reviews that were 5 stars versus non-Vine reviews were 5 stars:

Vine members gave 454 out of 1,080 reviews a 5 star rating.
Non-Vine members gave 23,034 out of 49,659 reviews a 5 star rating.

3. Percentage of Vine reviews that were 5 stars versus percentage of non-Vine reviews were 5 stars:

  42% of the reviews for Vine members were rated 5 stars.
  46.4% of the reviews for Non-Vine members were rated 5 stars.

Summary

Vine members did not show bias when rating products. The number of 5-star ratings were less than Non-Vine members. With this, we can assume that Vine customers are more critical when submitting their review. However, in order to support this assumption further, we should include all of the data rather than filtering it to a percentage of helpful vs. total votes as we did for this analysis. Reviewing the data as is would give us more information and allow us to further support our assumption as shown below.

nonfilteredtotal

In addition, running the same analysis using datasets from different product categories can provide us with the whole picture of whether reviews made by Vine members are bias.
