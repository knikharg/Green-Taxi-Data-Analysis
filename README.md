# Green Taxi Data Analysis
## Abstract 
The Taxi Limousine Commission(TLC) provided yellow taxi service for the city of New York. But these taxi services were concentrated to the Manhattan region of the city and did not ride to the outskirts. The green taxi service was hence initiated to cater to the demands outside of Manhattan which started in 2013. The data is vast and there are various conclusions we can draw from it. We aim to maximize the revenue of the company by implementing various machine learning techniques of supervised and unsupervised algorithms to identify the ideal model to the data.

##  About Data
The dataset is about TLC green taxi service for years 2016 to 2018. The data is consolidated from NYC Taxi Limousine Commission for each of the above years. The data set consists of 19 columns, which consist of numerical and categorical values. There are total of *22.5* million instances overall. The domain of the dataset is Public Transportation.

[TLC Trip Record Data](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
[Green Trips Data Dictionary](https://www1.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_green.pdf)

## Data Pre-processing

1. Raw data is a monthly data which we consolidated by year.
2. Next, we combine all 3 years (June 2016 – June 2019) dataset into a single dataset which results into 22.5 million instances.
3. Valid Data:
    1. ‘tolls_amount’ – Since toll amount cannot be negative, we are filtering positive values for toll amounts.
    2. ‘fare_amount’ – Since the initial base fare charge is $2.5, we have taken fare amount values greater than or equal to $2.5.
    3. ‘passenger_count’ – Since an XL ride can take up to 6 passengers, we have limited the maximum passenger count to 6.
    4. ‘RatecodeID’ – Valid Rate code ID range from 1-6. Hence, a constraint has been put to remove any invalid category values
    5. ‘trip_distance’ – Rides whose trip distance lesser than or equal to zero are considered as cancelled rides. Hence, trip distances                            which are greater than zero are considered.
4. Date and Time format: ‘lpep_pickup_datetime’ and ‘lpep_dropoff_datetime’ store pickup and drop off date and time of every unique ride. Each of these columns were separated according to year, month, day, hour and minutes.
5. Dropped columns:
    1. ‘ehail_fee’ – This column consists entirely of zeros values which can be ignored.
    2. ‘lpep_pickup_datetime’ – Since date and time of pickup of customer has been incorporated by the separate columns created for year,                                   month, date and time, this column for removed.
    3. ‘lpep_dropoff_datetime’ - Since date and time of drop off of the customer has been incorporated by the separate columns created for                                  year, month, date and time, this column for removed.
