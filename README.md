# Prosper Loan Data Exploration

## Dataset
The data set consists of Loan Details of Borrowers at different points in time.
The dataset is a very interesting one, with a dimension of 113937 observation and 81 features.
The data set has features like Prosper Rating, Listing, Borrower Rate, Loan Status, Loan Status, Monthly Income etc.
The dataset can be found [here](https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv&sa=D&ust=1581581520570000)
The dictionary that explains all the features can be gotten here [here](https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&ust=1554486256024000)



## Summary of Findings
I divided the Data Analysis process into the following sections
1. Data Wrangling which includes data gathering, Data Cleaning and Exploratory data analysis. Under the data cleaning section, i Assesed the data, Cleaned and  Confirmed all the cleaning processes accordingly.

I discovered that in the data set, there are certain Data quality and Data Tidyness issues which will affect my analysis if i do not deal
with them.
Some of the Data Qualty issue i found out are:
1. missing values
2. duplicate values
3. non descriptive variables
4. wrong data types
5. Outliers
Since some of the data are numerical/quantitative and some are categorical/qualitative so i dealt with the missing values appropriately,
I used median values to fill the missing values of numerical variables instead of using mean because median can withstand extreme values 
compared to mean.
But before filling the missing values accordingly, i plotted a bar chart to view the count of missing values in each varible that
has missing values.
I also used the modal of categorical variables to fill them accordingly.
I noticed that some of the columns are irrelevant for proper analysis, so i dropped the columns. I renamed the variables for proper description.
Since some of the variables have some wrong data types, i used the .astype function to change data types acordingly and make categorical 
columns categorical, numerical columns numerical. 
In the "Occupation" column, i filled the missing values with "No_occupation"
I also discovered that some varibles have duplicates values, hence, used an appropriate function to to remove every duplicate values.

It was important for me to run the summary statistics of the data set and i discovered a few things after using the "describe" function to
check the summary statistics.
The mean of the "Term" column is greater than the median , which means that it is right skewed, looking at the minimum and maximum of the feature, (12,60) and the standard deviation, it shows that the spread of the data points from the mean are a bit wide but still reasonble.
"BorrowerRate" feature is also right skewed with little difference between the minimum and maximum data points.
Monthly Income,OnTimeProsperPayments and Amountof_Loan are also right skewed.
Before entering the exploratory Phase, i used a heatmap to show how each feature are correlated with each other.

In the Exploratory Data Analysis section i discovered the following:

On plotting the distribution graph of DelinquenciesLast7Years and OnTimeProsperPayments, i discovered that OnTimeProsperPayments and
DelinquenciesLast7Years are unimodal and right skewed, with longer tail to the right after i used a proper function to show necessary plots.

In the count plot, it was obvious that the loan borrowers with current loan status have the highest count, followed by the completed while 
those with past due(>120 days) have the least count.

From another countplot, there are more Loan borrowers who are home owners than those who do not have home.
In the distribution plot of Monthly Income and Amount of Loan of Borrowers, i intentionally used a proper bin size instead of using just any how bin, and i aslo created a small width in the Amount of Loan  column, so that analysis can be easier. The Amount of Loan is a multimodal
distributin while Monthly Income is unimodal.

From the Bivariate Exploration between BorrowerRate and MonthlyIncome , it is obvious that there is a stronger relationship at borrower rate value of 0.15.
The color palette i used is sequential, where i applied the inverse of viridis which i assigned to the cmap function and i used a cmin so that positions with correlations not up to 0.5 will not be shown.

I used a groupby clause to show the loan status of borrowers and their average monthly income. I found out that loan borrowers with loan status of Payment in Progess have the highest average monthly income.

I also looked into the Realtionship between loan status and the interest rate on the amount given to borrwers, i found out that borrowers that have loan status of chargedoff and defaulted have highest borrower rate, while Final Paymnet in progess have the least.

From the Multivariate Exploration:

From the scatter plot of relationship between Amount of Loan, Monthly income and considering current and completed loan status, i found out that the margin between between the monthly income of borrowers who are still currently paying and those who have completed payment is not too significant, except for some outliers at some extreme points. I used 'shape' to introduce the categorical variable(Loan Status) since shape is much better when plotting three variables where the third one is a categorical variable like i have in my case.

I also found out that the relationship between between borrower rate, and amount of loan for current, completed and final payment in progress loan status varies with the brrowers rating. There are fewer borrowers who are paying their fianl money and with a rating of AA while there are clusters of different data points representing borrowers, whose loan status are current and completed across all the ratings.

My use of colors has been very intentional, even considering people with  eye blindness.

I looked into how being a home owner can affect borrower rate and loan status and i discovered a few patterns:
i found out that most of the borrowers who do not have homes even have higher borrower rate than those who have homes.
it was only borrowers whose payment has past due 120 days and have homes that have a little gap of borrower rate than those who do not have home.




## Key Insights for Presentation

In this section of my presentation, i firstly focused on the distribution of Delinquency of last seven years and that of on time prosper payments.
i used a function here so that in cases where the data points in the variables are negative , it will not affect my visual analysis or distribution. The bins too are very intentional because just picking a random bin value distorted my visuals, so i had to run a summary statistics of each feature and choose a suitable bin based on the minimum and maximum values of the features.
You will notice that both histogram plots are unimodal and right skewed, with delinquency of last seven years having very long tail to the right of the plot and some very little counts below 2000 from 5 to values befor 100.

I there after, looked into the relationship between Loan Status and Proper rating using a heatmap and bar chart side by side for easy comparison.  From the heat map, i used lighter regions to show very strong correlation between variables while darker regions show small correlation. I found out that the strongest relationship between lan status and prosper rating occur where the loan status is current and the rating is A while the region with the least correlation is at loan status of current and rating HR.

Looking further at the bivariate analysis where i plotted a violin plot and a box plot side by side in order to compare their in depth distribution and explration.

Generally i found out that i had to compare different plots in some sections so that comparison can be perfect and i also used transformations where necessary. The use of color was not just random, i followed the proper way according to each color pallets.

