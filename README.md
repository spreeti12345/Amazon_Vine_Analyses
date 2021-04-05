# Overview
We will examine reviews of Kitchen items dataset from Amazon Vine program.
The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products.
Companies subscribe to this service by paying a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.
All the Vine dataset share a common schema with the same table titles.
Amazon review dataset schema We use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. We then use Pandas to determine if there is any bias towards favorable reviews from Vine members in the dataset.

## Resources
Amazon reviews from https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Kitchen_v1_00.tsv.gz"
Google Colab Notebook
Jupyter Notebook
Pysparks
pg Admin
postgres
AWS console- RDS

## Summary
For the analsyis we used the below variables from our Kitchen items dataset
Vine table
<img width="458" alt="Initial" src="https://user-images.githubusercontent.com/74282781/113541941-0ec08e00-9598-11eb-9150-e6396fbf041d.png">


We then peform the following transforms to the dataframe:
1- Select only the records where the total votes was equal or greater than 20

<img width="516" alt="over 20%" src="https://user-images.githubusercontent.com/74282781/113541957-197b2300-9598-11eb-9d7c-7fc9bcb796f4.png">

2- From the selection in step 1 choose only the records where percentage of helpful votes is equal or greater than 50%.

<img width="510" alt="50%" src="https://user-images.githubusercontent.com/74282781/113541965-1f710400-9598-11eb-93f8-d26e6c4bb0b9.png">

3- Calculate the total # of reviews, the # of 5-star reviews and the % of 5-star reviews for each member type

<img width="391" alt="Final review" src="https://user-images.githubusercontent.com/74282781/113541976-2730a880-9598-11eb-8ec3-75218c0a57b2.png">

We notice that the number of non member votes is larger than the member votes.

## Reviews by member type

When we look at the percentage of five star reviews between the two categories they are close- but the non vine members reviews is 4% higher than Vine member reviews.
This leads us to the conclusion that there is is no bias towards member reviews in the Vine program.






