# Module 5 Project
## In this project I am trying to analyze the provided data to check if customer will accept coupons or not 


### There are two files in this repository
#### 1.Readme.md
#### 2.project.ipynb
<br>

## Problem 1. Read in the coupons.csv file.
Solution : 
1. Used the pandas **read_csv** method to read the csv file provided as part of the Project and storing the data in the '**data**' object of type data frame.
2. Check the size of the dataset using **data.shape** method. It has 12684 rows and 26 columns

![Read csv file and show number of records.](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob1-Pic1.png)

3. Showing first few rows of the data using the data.head() method
   ![Screen shot displays first 5 records of the data](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Probl1-Pic2.png)
 
## Problem 2. Investigate the dataset for missing or problamatic data.
Solution:
1. Used the **data[data.duplicated(keep=False)]** method to find the duplicate records, here in the param I am passing Keep = False to highlight all accurances of duplicate records. Then finding the total nomber of duplicate records by using the shape attribute of the series. Store row count in variable **duplicatesCount**

 ![Screen shot displays number of duplicate records in the data](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob2-Pic1.png)

2. Used the method **data.Info()** to know the type of the columns.  
   ![Showing data type for each column](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob2-Pic2.png)

Then checked the unique values in each column explore. Observed that Data in few column type doesn't align with the type. For e.g. Age should be integer. It has values 50plus and below21
   ![Showing age have mixed of integer as well as character values](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob2-Pic3.png)


3. Used the method **print(data.isnull().sum())** to find the count of missing records for each column. I found that there are 6 columns with missing records
   car                     12576
   Bar                       107
   CoffeeHouse               217
   CarryAway                 151
   RestaurantLessThan20      130
   Restaurant20To50          189

![Screenshot shows columns with missing data](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob2-Pic4.png)

## Problem 3. Decide what to do about your missing data -- drop, replace, other...
Solution:

1. Ignoring missing data in Column "Car" as it shouldn't impact my analysis
2. For all other columns, I am replacing the missing record by never. This is because the number of missing records when the 
   coupon is of  that type is negligible
   For e.g the total number of records where Coupon ==  Bar is 
           the total number of records where Coupon == Bar and Bar isNull =  
which is negligible. Similar is the case for other columns. So I will replace all these missing records with never
