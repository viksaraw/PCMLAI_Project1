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

1. Drop all the rows with duplicate records<br>
   ![Dropping duplicate records fromd data](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob3-Pic1.png)
   
3. Ignoring missing data in Column "Car" as it shouldn't impact my analysis
4. For  other columns,  **replacing the missing record by never**. This is because the number of missing records when the 
   coupon is of  that type is negligible <br><br>
   
   Replacing all the 5 columns with blank records with value = 'never'
   ![Code showing replacing 5 columns with blank records with value = 'never'](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob3-Pic4.png)

4. For the Age Column, for the ease of filtering, I am replacing age values of 'blow21' and '50plus' by 20 and 51 
   respectively and changed the column type to int
   ![Screenshots ](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob3-Pic5.png)
   
## Problem 4.  What proportion of the total observations chose to accept the coupon?
   <br> **Ans - 56.75%**

Solution :
To find the proportion of the total observations chose to accept the coupon
   1. First find the total count.
   2. Second find the count of passangers who accepted where Y==1
   3. Then divide the accepted count to the total count

![](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob4-Pic1.png)

## Problem 5. Use a bar plot to visualize the `coupon` column.

Solution:
To create a bar plot to visualize the coupon column, I have first created a data set with  count of each coupon type from the data dataset
![screen shot displays the count for each type of coupon](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic1.png)

Then Use the barplot method from seaborn to create a barchart, showing different colors for each bar by selecting
hue = 'coupon'
![Screen shot for barplot code](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic2.png)

![Screenshot for barplot text](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic3.png)

![Screenshot of barplog](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic4.png)

 Histogram for coupon also done by using histplot method from seaborn
![Screenshot for histogram of coupons](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic6.png)
![Screenshot for histplot data](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic7.png)
![Screenshot for histplot](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob5-Pic8.png)

## Problem 6. Use a histogram to visualize the temperature column.
Solution : I have used the seaborn histplot method to plot temperatures
![screenshot for histogram of temperatures](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob6-Pic1.png)


# Investigating the Bar Coupons

<br>Now, we will lead you through an exploration of just the bar related coupons.  
## Problem 1. Create a new `DataFrame` that contains just the bar coupons.
Solution:
From the data, querying out data where coupon == Bar and putting in new data frame named DataBar
![screenshot contains code to create a new data frame that contains just the bar coupons](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob7-Pic1.png)

## Problem 2. What proportion of bar coupons were accepted?
<Ans> 40.99% of bar coupons were accepted
Solution:
To find this proportions following steps have been taken

   1. Find the total Bar Coupon Count
   2. Find the count of Bar Coupons that were accepted
   3. Find the proportion by dividing 1 with 2

Screenshot shows all the 3 steps
![screenshot to show the proportion of bar coupons accepted](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/Prob8-Pic1.png)

## Problem 3. Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.
Solution:
1. Find count of passangers who visited bar 3 or fewer times i.e. between 1 to 3 times and accepted the coupon
2. Find count of passangers who visited bar 3 or fewer times i.e. between 1 to 3 times
3. Divide 1 with 2 to find the acceptance rate who visited bar 3 or fewer times
![Accepted rate for less than 3 times visitors](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob3-Pic1.png)
4. Find count of passangers who visited bar more than 3 times and accepted the coupon
5. Find count of passangers who visited bar more than 3 times
6. Divide 4 with 5 to find the acceptance rate who visited bar more than 3 times
![Accepted rate for more than 3 times visitors](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob3-Pic2.png)

### Conclusion: Comparing these - Clearly the acceptance is higher for drivers who visit bar more than 3 times
![Compare the acceptance rates](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob3-Pic3.png)
  
## Problem  4. Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others.  Is there a difference?
Solution:
1. Find the count of drivers who go to a bar more than once a month and are over the age of 25 and accepted coupon
2. Find the count of drivers who go to a bar more than once a month and are over the age of 25
3. Divide 1 with 2 to find the acceptance rate
![Accepted by Customers](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob4-Pic1.png)
4. Find the count of other drivers accepted coupon
5. Find the count of other drivers
6. Divide 4 with 5 to find the acceptance rate
![Accepted by other drivers](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob4-Pic2.png)
   
### Conclusion: Comparing these - Clearly the acceptance is higher for drivers who go to a bar more than once a month and are over the age of 25
![Compare the acceptance rates](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob4-Pic3.png)


## Problem 5. Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry.
Solution:

1. Find the count of drivers who meet all 3 conditions and accepted coupon
2. Find the count of drivers who meet all 3 conditions
3. Divide 1 with 2 to find the acceptance rate
![Accepted by Customers](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob5-Pic1.png)
4. Find the count of other drivers accepted coupon
5. Find the count of other drivers
6. Divide 4 with 5 to find the acceptance rate
![Accepted by other drivers](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob5-Pic2.png)
   
### Conclusion: Comparing these - Clearly the acceptance is higher for drivers who meet the 3 conditions
![Compare the acceptance rates](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob5-Pic3.png)


## Problem 6 Compare the acceptance rates between those drivers who:<br>

- go to bars more than once a month, had passengers that were not a kid, and were not widowed OR
- go to bars more than once a month and are under the age of 30 OR
- go to cheap restaurants more than 4 times a month and income is less than 50K.

Solution:
Below steps have been taken to find the solution

1. Storing values in array for easier querying later
   ![Variable storage](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob6-Pic1.png)
2. Creating the conditions
   ![Condition forming](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob6-Pic2.png)
3. Find the count of drivers who doesn't meet any of the 3 conditions and were offered
   ![Count ](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob6-Pic3.png)
   
5. Find the count of drivers who meet 3 conditions and accepted<br>
   ![Count_meet_Cond](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob6-Pic4.png)
   <br>
7. Find the acceptance rate<br>
   ![Acceptance Rate](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/CP-Prob6-Pic5.png)

**********************************************************************************************************************************


## Independent Investigation

Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons. 
1. Finding the Acceptance  Rate of drivers who  visits high income restaurant more than 3 times a month vs others

   To acheive this - following steps have been taken
  - a. Make arrays of High Income and low Income groups for ease of querying
  - b. Find the count of drivers who accepted high income restaurant
  - c. Find the count of drivers who were offered high income restaurant
  - d. Find the acceptance rate
   ![Acceptance rate of drivers visit](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic1.png)
   
  - e. Find the count of drivers who accepted high income restaurant and they visit high end restaurant more than 3 times a month
  - f. Find the count of drivers who were offered high income restaurant
  - g. Find the acceptance rate
  - ![visits more than 3 times a month](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic2.png)

### Analysis 1 - Drivers who visit high end restaurant more than 3 times a month are more probable to accept coupons of high end restaurant

To further analyze I am plotting the kind of drivers accepting Coffee House Coupons
To do this analysis, I have taken these steps
-a. Select all the records where coupon == 'Coffee House' and put it in another data frame say 'coffee'
![Coffee house data frame](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic3.png)
-b. Then plot a histogram on 'coffee' where x= Passanger type
![Histogram Plot](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic4.png)

### Analysis 2 - Drivers who are alone or with friends visits coffee house the most


Further Analysis to find the visitor of coffe house based upon occupation
Again I am doing a histogram and plotted on 'Coffee' where x='occupation'<br>
![Histogram code](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic5.png)
![Histogram display](https://github.com/viksaraw/PCMLAI_Project1-Pictures/blob/main/IP-Pic6.png)

### Analysis 3 - Unemployed, Students and Computer and Mathematical are the three occupation who visited COffee house the most

## Conclusion of Independent analysis
- 1.Drivers who visit high end restaurant more than 3 times a month are more probable to accept coupons of high end restaurant
- 2.Drivers who are alone or with friends visits coffee house the most
- 3.Unemployed, Students and Computer and Mathematical are the three occupation who visited COffee house the most
