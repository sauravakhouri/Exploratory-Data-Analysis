# Data-Analysis-Google-Apps-Rating-
Used Python (Pandas, Matplotlib) for cleaning data and  basic visual analytics. Rating, Prices and Reviews have been analysed by App categories using a Kaggle dataset on Google Apps.

Steps:

Preparation:

1) Download Data from Kaggle
2) Read Data in a dataframe using Pandas
3) Head() or tail method to check a few rows to see  how the data looks
4) Shape() to check the number of rows and columns of the data in the dataframe
5) Use the describe method to check Summary Statistics, which also gives idea of the columns where central limit thorem is applied and if more columns need to numeric.
6) Box plot to check how the data is distributed, if an outlier is found, investigate and fixif needed. In this case and outlier was found.
7) Plot a histogram to check the skewness of data and fix it. Skewness was not clealy visible in the initial stage however indicative of a left skewed data.

Data Cleaning:

8) Find the null values from the dataframe using isnull() method of pandas
9) Using sum() along with isnull() gives count of null values along with the respective columns
10) Since Google rating cannot be more than 5, and the box plot from point(6) showed an outlier, it's clear that the outlier data is incorrect, hence fixing is needed.
  10.1) The outlier row is dropped as it has incorrect data, using drop() method using index and inplace=True argument to make change to the existing dataframe
  10.2) Rechecked to make sure if the row is dropped using conditions or slicing the range of the dataframe
11) Replot the boxplot to check the new distribution after the outlier was removed.
12) Replot Histogram and it clearing shows the data it left skewed after the outlier is handled.
  12.1) Skewed data may be because of missing values in columns, hence we would use median to fill out those missing values as our data is skewed.
13) But first we need to remove columns which have insufficient data(90% empty) from our anlysis.
  13.1) We define a threshold of 10% by using the total number of rows.
  13.2) We drop all the columns with less than 10% of the data(threshold) using dropna() method, axis=1 is set because we want ot get rid of column
  13.3) We check the columns again to make sure it is dropped, but in this case it is not as all the columns have sufficient data
14)Perform Data Imputation and Manipulation to fill the missing/null values using mean/median//mode. Median/Mean is used for numerical data and mode for categorical. Median in this case as it's a Skewed data.
  14.1) Write a function to take in each row for the selected column(as Series) and if it is found to be full,fill it with median using fillna() method
  14.2) Use transform method to apply the operation by passing the function.
  14.3) Recheck if all the null values of the selected column is handles or not
15)Now if there are other missing values, handle them as well. In this case, few categorical values have missing values. Handle them using mode as per(14)
  15.1) Find the modes of the required columns using mode() method.
  15.2) Using the fillna() method, fill the missing values with mode. Use mode.value[0] to select first mode for cases of bimodal column.
  15.3) Recheck if any null values are handled or not


Data Analysis(through Visualization):
Preparation:

16) Since from step (5) and onwards, we know there is only one column in numerical format and we need need more numerical data fro proper analysis hence we convert the relevant columns for Data Analysis. We will convert Reviews, Price and Installs Columns to numerical format
  16.1) Fix the Price Column by handling Dollar and Comma sign using replace($ with '') & typecasting from str to float with lambda function
  16.2) Reviews are already only digits, hence convert them focibly(error=coerce) to numberic using to_numeric method of pandas
  16.3) Fix Installs similar to Price by handling '+' sign and ',' sign
 17) Check if the changes are done and use the describe() method to check the summary stats of all the new numeric columns.
 Plotting:
 18) Understand the question you're looking to answer and plot data accoding to the question
 19) Here we want to analyse the Google Apps Rating,Reviews,Price by their Categories
   19.1) Create a Group by Categories using groupby function
   19.2) Aggregate the columns/measures based on what you're looking for. In this case Mean of Rating & Reviews & Sum of Price is taken by Category group
 20) Move ahead to the final step of plotting the data for a visual analytics.
  20.1) Define the size of the canvas using figure(figsize) or subplots(figsize)
  20.2) Plots bubbles to show the category wise Rating(with category on X axis and rating on Y) using matplotlib plot() method
  20.3) use xticks() to rotate names on x axis, set title(), xlabel() and ylabel() to set title and labels for x and y axis
  20.4) show() function to show the graph and not the unwanted information
  20.5) Repeat the same with all the variables and study the graph for a conclusion.
  
Conclusion:
The analysis through the visualizations show that:
1) Education and Events Apps have some of the highest rating while Dating Apps have the lowest.
2) Overall Price of Finance, Family, Lifestyle and Medical Apps are the highest.
3) Number of Reviews on Social, Communication and Gaming apps are among the highest  
