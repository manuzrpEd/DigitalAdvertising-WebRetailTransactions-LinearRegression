# Total Web Transactions & Retail Transactions

This assessment is designed to help show my coding competency, reasoning/analysis capabilities, and communication skills. The main objective is to be able to turn my insights into realistic business actions. It would be beneficial to make appropriate recommendations if/where possible. My assessment attempt is [here](https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/Web%26RetailTransactions.ipynb).

Given the accompanying sample dataset, I am tasked with performing any analysis that I see fit that will help answer the following question: What activities should be performed (i.e. increased/decreased) in order to increase total Web Transactions without negatively impacting the number of Retail Transactions? 

Answer:
<p>
<li>
    1. Digital advertising variables, such as Affiliate Spend, Email Spend, Branded Search Spend and Unbranded Search Spend are associated with higher both Web Transactions and Retail Transactions.
    <p>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/AffiliateWT.png" alt="AffiliateWT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/AffiliateRT.png" alt="AffiliateRT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/EmailWT.png" alt="EmailWT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/EmailRT.png" alt="EmailRT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/BrandedWT.png" alt="BrandedWT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/BrandedRT.png" alt="BrandedRT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/UnbrandedWT.png" alt="UnbrandedWT"/>
    <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/UnbrandedRT.png" alt="UnbrandedRT"/>


</li>
<li>
    2. Of those 4 channels, Affiliate Spend is the channel with the largest impact. The response to percent increases in any of these channels is largest in magnitude for Affiliate Spend.
    <p>
    - A 1% increase in Affiliate Spend is associated with a 0.37% increase in Web Transactions, holding everything else constant.
        <p>
    - A 1% increase in Affiliate Spend is associated with a 0.19% increase in Retail Transactions, holding everything else constant.
</li>
<li>
    3. Firms would still have to ponder which channel is relatively more efficient for their specific marketing strategies.
</li>
<li>
    4. We would not recommend Percentage Discount as a means to increase Web Transactions as it is associated with lower Retail Transactions. At the very least, firms should ponder the trade-off that this action entails.
    <p>
        <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/PercentageWT.png" alt="PercentageWT"/>
        <img src="https://github.com/manuzrpEd/TotalWebTransactions-RetailTransactions/blob/main/PercentageRT.png" alt="PercentageRT"/>
</li>
</p>


Additional. Dataset Questions:

1.	Please note down if there was anything interesting or unusual that you noticed about the dataset. 
   * A few variables had inconsistent data types. For example, in some numeric variables a few entries had a string type.
   * Many variables have missing values. This creates the problem of how to treat missing values or whether to include these variables at all in the estimation.
   * The dataset has a rich variety of data types (integers, floats, categorical variables in string and date)
   * The data is a panel data set. The panel variable is Location ID, and the time variable is Date. This structure of the data allows for having more than one observation per Location ID (which increases statistical significance) and we can control for unobserved heterogeneity.
   * The time period is between the years 2005-2011. This means that some of the advertising channels may have been evolving/developing in later years.
2.	What data cleaning, if any, did you perform on the dataset?
  - Homogenise each variable to only one data type instead of having more than one, be it floats, integers or categorical data (in strings).
  - Fill in missing values: for spend variables I filled them with a 0, for categorical variables I added the category of 'Missing' whenever the entries were empty. For the model estimation, the filling of missing values bears no effect. This is because I use the Fixed Effect estimator that looks at deviations from the mean. In addition, I never incorporated Promo or Code variables to the model as most of these observations were missing.
  - For the model estimation, I transformed spend and transaction variables into logs, for better interpretation of the results (percentage increases/decreases).
  - I created dummy variables for year and month.
3.	What other information would you have liked to be included in your dataset? Explain what analysis you would have undertaken if you had those fields. Note down what you would have liked to do if given more time. 
  - I would have liked to have the corresponding CPI associated with the variables of Spend (£) as we do not know right now if we are working with real spend or nominal spend. The problem that this presents is that nominal spending may be going up due to inflation. So we may be making the wrong conclusions in this study. If I had CPI information, I would deflate the spend variables to work with real variables.
  - The result that Percentage Discount is positively associated with Web Transactions and negatitively associated with Retail Transactions is still not fully understood. Is the Percentage Discount only applicable online? I would have liked to know the rules for this discount.
  - If given more time, I would have experimented with other models of panel data (the structure of the data that we have) in order to check the robustness of the results. I think it is also important to have a radically different model structure to see if similar results hold. I could have also incorporated a few interactions of the variables. For example, I would have liked to interact Percentage Discount with a few of the months where Retail Transactions are lower to check if Percentage Discount is higher in those periods where firms anticipate to sell less.
