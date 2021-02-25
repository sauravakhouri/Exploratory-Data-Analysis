# Sales-Data-Analysis
Used Python Pandas and Matplotlib to analyze and answer some important business questions about 12 months worth of Sales Data of an electronic store. 

# Data Cleaning
Started by merging the data together in one file and then cleaning the data. Tasks during this section include:
- Drop NaN values from DataFrame
- Removing rows based on a condition
- Change the type of columns (to_numeric, to_datetime, astype)

# Business Questions
Once the data is cleaned up a bit, I've moved to the data exploration section. In this section I've explored 5 high level business questions related to the data:
- What was the best month for sales? How much was earned that month?
- What city sold the most product?
- What time should we display advertisemens to maximize the likelihood of customer’s buying product?
- What products are most often sold together?
- What product sold the most? Why do you think it sold the most?

# Answering the Business Questions
To answer these questions I've done some Exploratory Data Analysis and gone through many different pandas & matplotlib methods. They include:
- Concatenating multiple csvs together to create a new DataFrame (pd.concat)
- Adding columns
- Parsing cells as strings to make new columns (.str)
- Using the .apply()  and .transform() method
- Using groupby to perform aggregate analysis
- Plotting bar charts and lines graphs to visualize our results(dual axis chart)
- Labeling our graphs

I've explained each and every step in the code files for a detailed walkthrough and a better understanding.
