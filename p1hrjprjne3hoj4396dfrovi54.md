**[Creating S3 Buket:]{.underline}**

-   To begin, we establish a bucket called statefinance, a folder called
    stfolder, and two more folders called f1, f2, along with the csv
    files.

![](./image1.png){width="5.509995625546806in"
height="2.5549879702537184in"}

**[IAM ROLE:]{.underline}**

-   I have used the old IAM role

**[AWS Glue]{.underline}**

-   Since we have two input files, I have made two crawlers.

-   After that, I made one database specifically for crawlers.

![](./image2.png){width="6.016382327209099in"
height="1.069831583552056in"}

**[ETL Visual:]{.underline}**

-   The stages we are doing in ETL Visual are listed below.

![](./image3.png){width="5.166097987751531in"
height="1.441195319335083in"}

-   As a starting point, we\'re adding two S3 buckets.

-   To place the database and files that are already in the AWS Glue, I
    am utilizing the data catalog as the source in both AWS Buckets.

-   After adding the join, we will notice an overlapping issue, which we
    will fix by adding a right join.

![](./image4.png){width="3.2536898512685912in"
height="2.1616469816272965in"}

-   I used an inner join in the joins, selecting year for Amazon S3 and
    right_year for renamed keys. We\'ll have AWS Glue handle it through
    mapping.

-   The AND operator and the condition year\<=2000 are used in
    Conditional Routing.

![](./image5.png){width="2.522106299212598in"
height="2.2061318897637796in"}

-   For our data goals, we selected two AWS buckets.

-   For our data goals, we selected two AWS buckets.

-   We choose the Uncompressed compression type and Parquet format, and
    we keep the table I need to import our data into.

![](./image6.png){width="2.385483377077865in"
height="2.0083595800524936in"}
![](./image7.png){width="2.5303423009623796in"
height="2.1146511373578303in"}

-   Save the job now, then execute it. If it is successful, go to
    Athena.

![](./image8.png){width="5.0263976377952755in"
height="1.4673775153105861in"}

-   We use Athena to query the data catalog table.\
    \
    ![](./image9.png){width="3.792024278215223in"
    height="1.8825601487314085in"}

![](./image10.png){width="4.6015212160979875in"
height="2.3415452755905513in"}
