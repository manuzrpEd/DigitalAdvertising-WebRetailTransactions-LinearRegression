# TotalWebTransactions

This assessment is designed to help show my coding competency, reasoning/analysis capabilities, and communication skills. 

Given the accompanying sample dataset, I am tasked with performing any analysis that I see fit that will help answer the following question: What activities should be performed (i.e. increased/decreased) in order to increase total Web Transactions without negatively impacting the number of Retail Transactions? 

The main objective is to be able to turn my insights into realistic business actions. It would be beneficial to make appropriate recommendations if/where possible.

Dataset Questions

1.	Please note down if there was anything interesting or unusual that you noticed about the dataset. 
   * A few variables had inconsistent data types. For example, in some numeric variables a few entries had a string type.
   * Many variables have missing values. This creates a problem as with missing values the statistical significance (robustness) of the results worsens.
   * The dataset has a rich variety of data types (integers, floats, categorical variables in string and date)
   * The data is a panel data set. The panel variable is Location ID, and the time variable is Date. This structure of the data allows for having more than one observation per Location ID (which increases statistical significance) and we can control for unobserved heterogeneity.
   * The time period is between the years 2005-2011. This means that some of the advertising channels may have been evolving/appearing in later years.
2.	What data cleaning, if any, did you perform on the dataset?
  - Homogenise each variable to only one data type instead of having more than one, be it floats, integers or categorical data (in strings).
  - Fill in missing values: for spend variables I filled them with a 0, for categorical variables I added the category of 'Missing' whenever the entries were empty.
  - For the model estimation, I transformed spend and transaction variables into logs, for better interpretation of the results.
3.	What other information would you have liked to be included in your dataset? Explain what analysis you would have undertaken if you had those fields. Note down what you would have liked to do if given more time. 
