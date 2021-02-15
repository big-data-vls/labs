# Day 3 - Tech Challenge


## Pre-requisites:

Launch a EMR cluster 5.30.1 with Hadoop, Spark, Hive, Tez and Ganglia  in eu-central-1 region.

## Challenge-1

### dataset -  s3://gdelt-open-data/events/

### Schema:

| Column                | Data type |
|-----------------------|-----------|
| EventId               | DECIMAL   |
| Day                   | DECIMAL   |
| MonthYear             | DECIMAL   |
| Year                  | DECIMAL   |
| FractionDate          | DECIMAL   |
| Actor1Code            | STRING    |
| Actor1Name            | STRING    |
| Actor1CountryCode     | STRING    |
| Actor1KnownGroupCode  | STRING    |
| Actor1EthnicCode      | STRING    |
| Actor1Religion1Code   | STRING    |
| Actor1Religion2Code   | STRING    |
| Actor1Type1Code       | STRING    |
| Actor1Type2Code       | STRING    |
| Actor1Type3Code       | STRING    |
| Actor2Code            | STRING    |
| Actor2Name            | STRING    |
| Actor2CountryCode     | STRING    |
| Actor2KnownGroupCode  | STRING    |
| Actor2EthnicCode      | STRING    |
| Actor2Religion1Code   | STRING    |
| Actor2Religion2Code   | STRING    |
| Actor2Type1Code       | STRING    |
| Actor2Type2Code       | STRING    |
| Actor2Type3Code       | STRING    |
| IsRootEvent           | DECIMAL   |
| EventCode             | STRING    |
| EventBaseCode         | STRING    |
| EventRootCode         | STRING    |
| QuadClass             | DECIMAL   |
| GoldsteinScale        | DECIMAL   |
| NumMentions           | DECIMAL   |
| NumSources            | DECIMAL   |
| NumArticles           | DECIMAL   |
| AvgTone               | DECIMAL   |
| Actor1Geo_Type        | DECIMAL   |
| Actor1Geo_FullName    | STRING    |
| Actor1Geo_CountryCode | STRING    |
| Actor1Geo_ADM1Code    | STRING    |
| Actor1Geo_Lat         | DECIMAL   |
| Actor1Geo_Long        | DECIMAL   |
| Actor1Geo_FeatureID   | DECIMAL   |
| Actor2Geo_Type        | DECIMAL   |
| Actor2Geo_FullName    | STRING    |
| Actor2Geo_CountryCode | STRING    |
| Actor2Geo_ADM1Code    | STRING    |
| Actor2Geo_Lat         | DECIMAL   |
| Actor2Geo_Long        | DECIMAL   |
| Actor2Geo_FeatureID   | DECIMAL   |
| ActionGeo_Type        | DECIMAL   |
| ActionGeo_FullName    | STRING    |
| ActionGeo_CountryCode | STRING    |
| ActionGeo_ADM1Code    | STRING    |
| ActionGeo_Lat         | DECIMAL   |
| ActionGeo_Long        | DECIMAL   |
| ActionGeo_FeatureID   | DECIMAL   |
| DATEADDED             | STRING    |
| SOURCEURL             | STRING    |


### Problem statement:
1.	It needs to be partitioned by country
2.	We can only have one output file in each partition.
3.	You only need to put IN and SA in there (Only need to consider India and South Africa)
a.	IN – country code for India
b.	SA – Country code for South Africa
4.	Output needs to be written to  in your s3 bucket.
5.	Output needs to be in parquet gzip/snappy compressed format
6.	So in the end we’ll have something like below format
s3://bucket/output/country=IN/result

s3://bucket/output/country=SA/result


# Challenge-2

Use the Amazon Customer Review Data Set.
https://s3.amazonaws.com/amazon-reviews-pds/readme.html

### Dataset - s3://amazon-reviews-pds/tsv/

### Problem statement:
2.1	Transform the TSV data into JSON/Parquet. You can use any method or technique on the EMR cluster.

2.2	if Json/Parquet then justify the above method. The data needs to be partitioned by the year column.

2.3	Identify top 5 categories which has received 5 star ratings. Write down the code that you have  used to find the top5 categories.

2.4	Why you used specific application for this implementation.



# Challenge-3 

### Dataset - s3://amazon-reviews-pds/tsv/

### Problem statement:
Please use ‘s3distcp’  tool to copy the data from S3  to HDFS.

3.1	Compress the final output into gzip compress with final output size of 200MB for each file

3.2	Observe and write down runtime for the ‘s3distcp’  job

3.3	How many mappers and reducers executed in your job. Please explain, how map-reduce is being used in ‘s3distcp’ job

3.4	Tune the ‘s3distcp’ job to make it more faster and note down your shortest runtime

3.5	Please note down your observations for tuning ‘s3distcp’ job


# References:

https://docs.aws.amazon.com/emr/latest/ReleaseGuide/UsingEMR_s3distcp.html
