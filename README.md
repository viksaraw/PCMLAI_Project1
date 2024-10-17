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







