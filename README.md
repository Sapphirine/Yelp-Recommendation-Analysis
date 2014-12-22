# Yelp-Recommendation-Analysis
==============================

### Information Group: Yelp Recommendation Analysis

This is project created by Siddharth Boobna, Yash Parikh and Prateek Sinha for Big Data Analytics.

##### Siddharth Boobna

Department of Computer Science

Columbia University

ssb2171 [at] columbia [dot] edu


##### Yash Parikh

Department of Computer Science

Columbia University

yp2348 [at] columbia [dot] edu


##### Prateek Sinha

Department of Computer Science

Columbia University

ps2791 [at] columbia [dot] edu


### How to use this Project?

1. After downloading the source code from here and the dataset, you must first run the data extractor files found [here](./data_extractor)

2. The data extractor will create CSV files which can be used with Hive.
   Note: You may have to modify the extraction scripts to give the path and filenames of your choice. Also, you can modify the columns being selected to work with any dataset of your choice.

3. After the data has been extracted, you may run the Hive Script found [here](./hive_scripts) which __contains the recommendation algorithm__.

4. The output of Hive will go to S3. You will have to modify it to target your S3 bucket.

5. Next, you need to modify the REST_API [here](./rest_api/GetYelpRecos)

   a. You need to modify the [RecoLister.java](./rest_api/GetYelpRecos/src/org/bigdata/handlerequest/RecoLister.java) file to add your own AWS credentials and also the change the path in the bucket where the output of Hive goes.
   
   b. You can then upload the war file to your EC2 and hit the url http://your-ec2-url/RequestHandlerServlet?uid=some-uid-here&numBusinesses=5 to get the appropriate number of recommendations for that user.
   
   c. The result will be ontained in a json format and can be used with any UI to be displayed in a meaningful manner.
   
6. You can also use our UI code which maps our recommendation and displays a ranked list on side.
