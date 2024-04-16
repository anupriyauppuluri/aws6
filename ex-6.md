**Creating S3 Buket:**

- To begin, we establish a bucket called statefinance, a folder called stfolder, and two more folders called f1, f2, along with the csv files.

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.001.png)

**IAM ROLE:**

- I have used the old IAM role

**AWS Glue**

- Since we have two input files, I have made two crawlers.
- After that, I made one database specifically for crawlers.

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.002.png)

**ETL Visual:**

- The stages we are doing in ETL Visual are listed below. 

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.003.png)

- As a starting point, we're adding two S3 buckets. 
- To place the database and files that are already in the AWS Glue, I am utilizing the data catalog as the source in both AWS Buckets. 
- After adding the join, we will notice an overlapping issue, which we will fix by adding a right join.

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.004.png)

- I used an inner join in the joins, selecting year for Amazon S3 and right\_year for renamed keys. We'll have AWS Glue handle it through mapping. 
- The AND operator and the condition year<=2000 are used in Conditional Routing.

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.005.png)

- For our data goals, we selected two AWS buckets. 
- For our data goals, we selected two AWS buckets. 
- We choose the Uncompressed compression type and Parquet format, and we keep the table I need to import our data into. 

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.006.png)    ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.007.png)

- Save the job now, then execute it. If it is successful, go to Athena. 

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.008.png)

- We use Athena to query the data catalog table. 

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.009.png)    

  ![](Aspose.Words.5635f4cb-b46a-4b25-b9d2-4629dff9d3f0.010.png)

