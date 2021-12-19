# PySpark_Challenge </br>
## Module 16 </br>
ETL and analysis of Amazon Vine reviews with AWS, postgresql, PySpark, and Google Colab</b> 
# <b>About this Project</b> 
The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products.</br> Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members,</br> who are then required to publish a review.</br>We have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products.</br> We need to pick one of these datasets from S3 and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data through pgAdmin. </br>Next, We’ll use PySpark to determine if there is any bias toward favorable reviews from Vine members in our dataset. Then, We’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.</br>

# <b>Results</b> </br>
# Amazon_Reviews_ETL </br>
* The s3 dataset link:   "https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Wireless_v1_00.tsv.gz  </br>
* We’ll create an AWS RDS database with tables in pgAdmin, use the dataset from the Amazon Review datasets and extract the dataset into a DataFrame</br>
* Next,we transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin. </br>
* Then, we'll upload the transformed data into the appropriate tables and run  queries in pgAdmin to confirm that the data has been uploaded.</br>

# customers_table  </br>
![alt text](https://github.com/ramyasnl/PySpark_Challenge/blob/main/Images/customertable.png) </br>

# review_id_table</br>
![alt text](https://github.com/ramyasnl/PySpark_Challenge/blob/main/Images/review_id_table.png) </br>

# vine_table </br>
![alt text](https://github.com/ramyasnl/PySpark_Challenge/blob/main/Images/vinetable.png) </br>


# <b>Summary</b>
# Vine Review Analysis 
We started cleaning up the dataframe ,then we filtered our data frames that had at least 20+ votes and at least 50% of helpful votes, then filtered by those that had and did not had a vine review. Summary statistics showed that there could be biased among "Star Ratings" given the quantities of "vine" and "non-vine" reviews. There were about 65,000 records that did not have vine reviews, and only 600 records that did have vine reviews. Next, we calculated the percentage of 5-star ratings for both groups. 36% of Amazon reviews that were part of the vine program gave a 5-star rating.</br>

# Paid Vine DF </br>
![alt text](https://github.com/ramyasnl/PySpark_Challenge/blob/main/Images/vinedf.png) </br>

# Paid Vine Review</br>
Total_paid_number:</br>
613</br>
Paid_five_star_number:</br>
222</br>
Percentage_five_star_vine:</br>
0.3621533442088091</br>

# Non Vine Review</br>
![alt text](https://github.com/ramyasnl/PySpark_Challenge/blob/main/Images/nonvine.png) </br>

# Non Vine Review</br>
Total_Non Vine_number:</br>
64934</br>
Non Vine_five_star_number:</br>
30530</br>
Percentage_five_star_Non Vine:</br>
0.47016971078325687

# Conclusion </b></br>
36% of records that were part of the Vine program(paid) gave a 5-star rating.</br>
47% of records that were not part of the Non Vine program(unpaid) also gave a 5-star rating.</br>
There were significantly less records that had Vine than those records that did not had Vine,</br>so there is less possibility of bias in the Vine/Star-Rating reviews.
