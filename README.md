# Customer-Complaint-Analysis
The project is focused on analyzing customer complaints data using Python to understand complaint patterns, identify recurring customer issues, evaluate response and resolution process.

## Table of Content
- Project Overview
- Business Objective
- Dataset Description and information
- Data Cleaning and Preparation
- Feature Engineering
- EDA
- Relationship Analysis
- Key Findings and Insights
- Business Recommendations
- Limitations
- Conclusions
- Python Code

### Project Overview
This project focuses on analysing customer complaints data using Python to understand complaint patterns, identify recurring customer issues, evaluate response and resolution processes, and uncover areas where customer service operations can be improved.

The analysis involves data cleaning, feature engineering, exploratory data analysis (EDA), and relationship analysis to extract meaningful insights that can support data-driven business decisions.

### Business Objective

The primary objective of this project is to analyse customer complaints data to understand the nature, frequency, and distribution of complaints, assess customer service response patterns, and identify potential areas for operational improvement.

**The analysis aims to answer the following business questions:**
- What are the most frequently reported customer complaints?
- Which products, services, or complaint categories generate the highest number of complaints?
- How do complaint volumes vary over time?
- What proportion of complaints receive timely responses?
- Is there an observable relationship between complaint categories and timely responses?
- How are complaints distributed across different customer groups or submission channels?
- What patterns can be identified in complaint resolution and customer service performance?
  
The findings will help identify recurring customer concerns, monitor service response performance, and provide recommendations for improving customer experience.

### Dataset Description and Information

The dataset contains customer complaint records, including information about complaint submission dates, customer issues, products or services involved, communication channels, and company responses. 

**Dataset Information**
- Tools used: Python
- Libraries: Numpy, Matplotlib, Seaborn, Pandas.
  
The dataset is from Maven analytics [Click here](https://mavenanalytics.io/data-playground/financial-consumer-complaints)

| Table | Description |
|------|------|
| Complaint ID | Unique identification of a complaint |
| Submitted via | How the complaint was submitted |
| Date submitted | The date CFPB received the complaint |
| Date received | The date CFPB sent the complaint to the company |
| State | Mailing address state associated with the complaint |
| Product | Type of product identified by the complaint |
| Sub-product | Type of sub-product identified (not all sub-products have a product) |
| Issue | Issue identified by the complaint |
| Sub-issue | Sub-issue identified by the complaint (not all sub-issues have an issue) |
| Company public response to customer | Pre-set list of options used to reply to the customer publicly |
| Company response to customer | How the company responded to the complaint |
| Timely response | Indicates whether the company responded on time (Yes/No) |

### Data Cleaning and Preparation

Data cleaning was performed to improve data quality, consistency, and reliability before conducting the analysis.

***The following activities were carried out:***
- Data Inspection: Examined the dataset structure, column names, data types, and general information.
- Duplicate Check: Identified and assessed duplicate records.
- Missing Values: Examined missing values across columns and determined appropriate handling methods based on the nature of each variable.
- Data Type Conversion: Converted date-related columns into appropriate datetime formats.
- Text Standardization: Cleaned text fields by removing unnecessary spaces and standardizing inconsistent entries.
- Category Inspection: Examined unique values in categorical columns to identify inconsistencies and variations.
- Data Validation: Checked the cleaned dataset for inconsistencies and confirmed that variables were suitable for analysis.
  
Missing values were not automatically replaced with arbitrary values where the original information could not be established. Existing missing records were retained or handled according to their analytical relevance.

### Feature Engineering

Feature engineering was performed to create additional variables that would support more detailed analysis and improve the interpretability of the dataset.

***The following features were created:***

| Table | Description |
|---|---|
| Complaint Year | The year the complaint was submitted |
| Complaint Month No | Numerical representation of the complaint month |
| Month Name | Name of the month the complaint was submitted |
| Complaint Quarter | Quarter of the year the complaint was submitted (1, 2, 3, or 4) |
| Complaint Weekday | Day of the week the complaint was submitted |
| Processing Lag | Number of days between complaint submission and the date it was sent to the company |
| Issue Category | Grouping similar complaint issues into broader categories |
| Resolution Category | Grouping company responses to identify complaints that were fully resolved |

### Exploratory Data Analysis (EDA)

Exploratory Data Analysis was conducted to identify complaint patterns, understand customer concerns, and examine the distribution of complaints across different variables.

***Complaint Volume Analysis***

***Business Questions:***
- What is the total number of complaints recorded?
- How are complaints distributed across different products or services?
- Which products or services account for the highest complaint volume?
  
Analysis: Examined complaint counts across product categories using frequency tables and bar charts.

Interpretation: With a total of 62,516 complaints recorded, some products have high complaints while other are low. Checking/savings account is the product with 24, 814 complaints making it the highest.

***Complaint Trends Over Time***

***Business Questions:***
- How does complaint volume change over time?
- Which months recorded the highest and lowest complaint volumes?
- Are there noticeable increases or decreases in complaint submissions?
  
Analysis: Analysed complaint counts by year and month using time-series visualizations.

Interpretation: Complain volume increased over the years, July recorded the highest while February has the least.

**Monthly Complaint trend**
![Monthly Complaints Trend](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Monthly%20Complaints.png)

**Complain Volume for each month and year**
![Complain Volume for each month and year](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Complain%20Volume%20by%20month%20and%20year.png)


***Complaint Issue Analysis***

***Business Questions:***
- What are the most frequently reported customer issues?
- Which issue categories account for the largest proportion of complaints?
- Are certain complaint categories more common than others?
  
Analysis: Grouped similar complaint descriptions into broader categories and examined their frequency distribution.

Interpretation: Account and card management is the frequently reported issue and the largest proportion of complaints.

**Top 10 Complaints**
![Top 10 complaint issue](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Top%2010%20complaint%20issue.png)

**Issue Category**
![Issue Category](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Issue%20category%20distibution.png)


***Customer Service Response Analysis***

***Business Questions:***
- What proportion of complaints received timely responses?
- How are timely responses distributed across complaint categories?
- Which categories have relatively higher or lower timely response rates?
  
Analysis: Examined the existing timely response indicator using frequency counts and percentage distributions.

Interpretation: Over 80% of complaints received timely response, all categories have higher rate of positive response.

***Complaint Submission Channel Analysis***
***Business Questions:***
- Which channels are most frequently used to submit complaints?
- How does complaint volume differ across submission channels?
- Are certain channels associated with particular complaint categories?
  
Analysis: Examined complaint distribution across available submission channels.

Interpretation: The channel commonly used is Web, most account and card management issue were reported through the web. Complain volume differ in that some channels are frequently used while others like Email are not used frequently.

**Complaints vs submission channel**
![Complaints vs submission channel](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Complain%20vs%20submission%20channel.png)

### Relationship Analysis

Relationship analysis was conducted to explore patterns between selected variables and identify differences in complaint distributions across categories.

***The analysis focused on the following relationships:***
-	Processing lag vs submission channel:  Examine the days before complaints were sent across
![Processing lag vs submission channel](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Processing%20lag%20by%20submission%20channel.png)
  
-	Product vs Response: The response for each product
![Product vs Response](https://github.com/oyekolaqudirat-cmd/Customer-Complaint-Analysis/blob/main/Product%20vs%20response.png)
  
-	Submission Channel vs Issue Category:  Examine how complaint types vary across submission channels
-	Company Response vs Timely Response:  Compare response categories with timely response status
  
***Methods Used:***
- Cross-tabulation to examine complaint counts across variable combinations.
- Percentage distribution to compare categories with different complaint volumes.
- Heatmaps to visualize patterns in cross-tabulated data.
- Bar charts to communicate differences between categories.
  
### Key Findings and Insights

The analysis revealed the following findings:
- Complaint Distribution: Checking/Saving account is the product with most complain with 24,814 complaints.
- Recurring Customer Issues: The frequently reported issues are account and card management and payment and transaction issue with 40 and 17 percent respectively.
- Complaint Trends: The year with significant rise in complaints with 20% is 2022.
- Customer Service Response: All complains have over 90% record of timely response.
- Relationship Patterns: Product and response relationship: Company response did not vary across product as more than 90% of complains were resolved and extremely few are still pending. Relationship pattern between submission channel and processing lag indicated that most complaints were sent to the company by CFPB in less than one day.
          
These findings provide an overview of customer concerns and observed patterns in the complaint-handling process.

### Business Recommendations

Based on the findings from the analysis, the following recommendations are proposed:
- Address Recurring Complaints: Investigate frequently reported complaint categories to identify potential process, product, or service issues.
- Monitor Response Performance: Regularly track timely response rates to identify categories or periods where response performance differs.
- Improve Complaint Categorization: Maintain standardized complaint categories to support consistent reporting and monitoring.
- Strengthen Customer Support: Review complaint-handling processes for categories with relatively high complaint volumes or lower timely response rates.
- Establish Continuous Monitoring: Develop a recurring complaint analysis report or dashboard to monitor complaint volumes, response patterns, and emerging customer concerns.
- Investigate Customer Disputes: Review complaint categories with notable dispute patterns to understand potential gaps in communication or resolution processes.
  
These recommendations are intended to support customer service monitoring and inform further investigation into recurring customer concerns.

### Limitations

The analysis is subject to the following limitations:
- Missing values in some variables may limit the completeness of certain analyses.
- Complaint records reflect reported customer experiences and may not represent every customer experience.
- Grouping similar complaint descriptions into categories involves some degree of classification judgment.
- The dataset provides observational information; therefore, relationships identified do not establish causal explanations.
- The available variables may not capture all factors influencing customer satisfaction or complaint resolution.
  
These limitations were considered when interpreting the findings and developing recommendations.

### Conclusion

This project applied Python-based data analysis techniques to examine customer complaints, identify recurring issues, explore complaint trends, and assess customer service response patterns.

Through data cleaning, feature engineering, exploratory data analysis, and relationship analysis, the project transformed raw complaint records into meaningful business insights.

The findings provide a foundation for understanding customer concerns, monitoring complaint-handling patterns, and identifying areas that may require further investigation or operational improvement.

Overall, the project demonstrates the application of Python, Pandas, NumPy, Matplotlib, and Seaborn in solving business-related analytical problems and communicating data-driven insights.

### Python Code
``` Python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

#Importing excel file
df = pd.read_excel('/content/drive/MyDrive/Consumer_Complaints.xlsx')
df.head()

#Checking columns
for col in df.columns:
  print(col)
  print(df[col].unique())
  print()

df.describe()

#Checking for duplicate rows
#No duplicated rows
df.duplicated().sum()

#No duplicated complaint id
df['Complaint ID'].duplicated().sum()

#Replacing the null values in different columns
#Did not replace the null values in timely response as it might distort the data
df['Sub-product'] = df['Sub-product'].fillna('No Sub-product')
df['Sub-issue'] = df['Sub-issue'].fillna('No Sub-Issue')
df['Company public response'] = df['Company public response'].fillna('No public response')

#Checking for date received is higher than date submitted
#No record of received date lower lower tahn the submitted date
abnormal_date = df['Date received'] < df['Date submitted']
abnormal_date.sum()

#Feature Engineering
#Complaint date column
df['Complaint year'] = df['Date received'].dt.year
df['Complaint quarter'] = df['Date received'].dt.quarter
df['Complaint monthno'] = df['Date received'].dt.month
df['Complaint day'] = df['Date received'].dt.day_name()

#Processing days column
df['Processing lag'] = df['Date received'] - df['Date submitted']

#Complaint Resolution Category:
#Closed with explanation, Closed with monetary relief and Closed with non-monetary relief are grouped into
#Complaints with a completed response
#In progess belong to Complaints with pending response.
#Closed Is classified as Other or unavailable outcomes.
Resolution_category = []
for response in df['Company response to consumer']:

   if response in ['Closed with explanation', 'Closed with monetary relief', 'Closed with non-monetary relief']:
       Resolution_category.append('Complaint with complete response')

   elif response == 'In progress':
       Resolution_category.append('Complaint with pending response')

   else:
     Resolution_category.append('Other or unavailable outcome')

#Creating resolution category column
df['Resolution_category'] = Resolution_category
#Counting issue column
df['Issue'].value_counts()
#Created a dictionary for category complain
issue_categories = {

    'Mortgage Issues': [
        'Applying for a mortgage or refinancing an existing mortgage',
        'Struggling to pay mortgage',
        'Closing on a mortgage'
    ],

    'Account and Card Management': [
        'Problem getting a card or closing an account',
        'Closing your account',
        'Closing an account',
        'Getting a credit card',
        'Opening an account',
        'Managing an account',
        'Trouble using the card',
        'Trouble using your card',
        'Credit limit changed',
        'Managing, opening, or closing your mobile wallet account',
        'Overdraft, savings, or rewards features',
        'Problem with overdraft',
        'Problem with an overdraft',
        'Problem adding money'
    ],

    'Loan and Lease Issues': [
        'Getting a loan or lease',
        'Struggling to pay your loan',
        'Struggling to repay your loan',
        'Managing the loan or lease',
        'Getting a line of credit',
        'Getting the loan',
        'Getting a loan',
        "Was approved for a loan, but didn't receive money",
        "Was approved for a loan, but didn't receive the money",
        "Can't contact lender or servicer",
        'Dealing with your lender or servicer',
        'Problems at the end of the loan or lease',
        'Problem with the payoff process at the end of the loan',
        'Loan payment wasn\'t credited to your account',
        'Vehicle was damaged or destroyed the vehicle',
        'Vehicle was repossessed or sold the vehicle'
    ],

    'Payment and Transaction Issues': [
        'Lost or stolen check',
        'Trouble during payment process',
        'Problem with a purchase shown on your statement',
        'Problem with a purchase or transfer',
        'Other transaction problem',
        'Problem when making payments',
        'Money was not available when promised',
        'Wrong amount charged or received',
        'Unauthorized transactions or other transaction problem',
        'Problem with cash advance',
        'Lost or stolen money order',
        'Incorrect exchange rate',
        "Can't stop withdrawals from your bank account"
    ],

    'Fees and Charges': [
        'Fees or interest',
        'Unexpected or other fees',
        "Charged fees or interest you didn't expect",
        'Excessive fees',
        'Problem with a lender or other company charging your account'
    ],

    'Credit Reporting Issues': [
        'Incorrect information on your report',
        "Problem with a credit reporting company's investigation into an existing problem",
        'Improper use of your report',
        'Problem with fraud alerts or security freezes',
        'Unable to get your credit report or credit score',
        'Credit monitoring or identity theft protection services',
        'Identity theft protection or other monitoring services'
    ],

    'Debt Collection Issues': [
        'Took or threatened to take negative or legal action',
        'Attempts to collect debt not owed',
        'False statements or representation',
        'Written notification about debt',
        'Communication tactics',
        'Threatened to contact someone or share information improperly'
    ],

    'Fraud and Security Issues': [
        'Fraud or scam',
        'Identity theft'
    ],

    'Customer Service and Communication': [
        'Other service problem',
        'Problem with customer service',
        "Problem with a company's investigation into an existing issue"
    ],

    'Marketing and Advertising': [
        'Advertising and marketing, including promotional offers',
        'Advertising',
        'Confusing or misleading advertising or marketing'
    ],

    'Other Product and Service Issues': [
        'Other features, terms, or problems',
        'Confusing or missing disclosures',
        'Problem caused by your funds being low',
        'Problem with additional add-on products or services',
        'Struggling to pay your bill'
    ]
}

#Convert it into mapping dictionary and creating a column with it
issue_mapping = {
    issue: category
    for category, issues in issue_categories.items()
    for issue in issues
}
df['Issue_Category'] = df['Issue'].map(issue_mapping)

#Checking if there is any issues that was not categorised
#Checking for null values
df[df['Issue_Category'].isna()]['Issue'].value_counts()
df['Issue_Category'].isna().sum()
df['Product'].unique()
df['Submitted via'].value_counts()

#Analysis
#Complaint Overview
#No missing Values
df['Complaint ID'].value_counts()
#Total Com plaint :62,516
df['State'].value_counts()

#Complaint count by submission channel
#The most used submission channel is the Web which over 45000 complains while the least is Email
df['Submitted via'].value_counts().plot(kind = 'bar')
plt.xlabel('Channel')
plt.ylabel('Count')
plt.title('Complaint Count by Submission Channel')
plt.show()

#Freqeuntly reported issue
df['Issue_Category'].value_counts(normalize=True)*100

#Time Trend
#Complaint trend over time
#The year with most complains is 2022
df['Complaint year'].value_counts(normalize=True).plot(kind = 'line')
plt.xlabel('Year')
plt.ylabel('Count')
plt.title('Annual Complain')
plt.show()

#Creating the month name column and ordering it by month order
df['Month_name'] = df['Date received'].dt.month_name()
#Creating month order
month_order = [
    'January', 'February', 'March', 'April',
    'May', 'June', 'July', 'August',
    'September', 'October', 'November', 'December'
]
df['Month_name'] = pd.Categorical(df['Month_name'], categories= month_order, ordered=True)
df = df.sort_values('Month_name')

#Monthly complaints
plt.figure(figsize=(10, 4))
sns.countplot(data=df, x='Month_name')
plt.xlabel('Month')
plt.ylabel('Count')
plt.title('Monthly Complaints')
plt.show()

#Quartely complaint distribution
df['Complaint quarter'].value_counts().plot(kind = 'bar')
plt.xlabel('Quarter')
plt.ylabel('Count')
plt.title('Quarterly Complaints')
plt.show()

#Complain volume by year and month
ys = pd.crosstab(df['Complaint year'], df['Month_name'])
sns.heatmap(ys, annot=True, fmt='d', cmap='Blues')
plt.title('Annual Complaints')
plt.xlabel('Month')
plt.ylabel('Count')
plt.show()

#Product Performance Analysis
#Checking/saving account received the highest number with 24814 complaints while student loan been 34 is the least.
#The sub product with the most complaint is checking account which has a fairly amount of positive response.
#Product by complain count
df['Product'].value_counts().plot(kind = 'barh')
plt.xlabel('Product')
plt.ylabel('Count')
plt.title('Product Performance')
plt.show()

#Sub product by timely response
df[['Sub-product', 'Timely response?']].value_counts().head().plot(kind = 'barh')
plt.xlabel('Sub-product')
plt.ylabel('Count')
plt.title('Product Performance')
plt.show()

#The most frequent report issue with each product
df[[ 'Issue', 'Product']].value_counts().head(10)

#Monthly complaint trend for selected product
df[df['Product'] == 'Checking or savings account']['Month_name'].value_counts().plot(kind = 'line')
plt.xlabel('Month')
plt.ylabel('Count')
plt.title('Monthly Complaints for Student Loan')
plt.show()

#Complaint Issue Analysis
#Rank issue by frequency and their percentage
df['Issue_Category'].value_counts().head().rank(ascending=True)
#Percentage
df['Issue_Category'].value_counts(normalize=True)
#OR
counts = df['Issue_Category'].value_counts()
percents = (counts / counts.sum()) * 100
print(percents)

#Issue group distibution
df['Issue_Category'].value_counts().plot(kind='barh')

#Top 10 issue complaint
df['Issue_Category'].value_counts().head(10).plot(kind='barh')
plt.xlabel('Issue')
plt.ylabel('Count')
plt.title('Top 10 Issue Complaints')

#Compare issues across years
#There was a peak in all complains in 2022 and 2017 has the least of complaints
df[['Complaint year', 'Issue_Category']].value_counts().unstack().plot(kind = 'line', stacked=True)
plt.xlabel('Year')
plt.ylabel('Count')
plt.title('Annual Complaints')
plt.show()

#Issue vs submission channel
#Web: Account and card management accounts for the most issue vs submission channel
df[['Issue_Category','Submitted via']].value_counts().head().plot(kind = 'barh', stacked= True)
plt.xlabel('Channel')
plt.ylabel('Count')
plt.title('Issue vs Submission Channel')
plt.show()

#The common sub issue in issue category is deposits and withdrawal with 5596 complains.
df[['Issue_Category', 'Sub-issue']].value_counts().head()

#Geographical Analysis
#State with the highest and lowest complaint count
#CA accounts for the highest complains of 13,709 with 21%
#while WY and ND has the lowest of 22 with 0.035%
df['State'].value_counts()

#Percentage
counts = df['State'].value_counts()
percents = (counts / counts.sum()) * 100
print(percents)

#Complain issue distibutes by state
df[['State', 'Product']].value_counts()

#Product category across various state
df[['State', 'Issue_Category']].value_counts().head()

#Company Response Analysis
#Counting null response
df['Timely response?'].isna().sum()

#Timely nv non timely Response
counts = df['Timely response?'].value_counts()
percent = ((counts / counts.sum()) * 100).plot(kind='bar')
plt.xlabel('Timely Response')
plt.ylabel('Count')
plt.title('Timely Response')
plt.show()

#Company response to consumer
df['Company response to consumer'].value_counts().plot(kind='barh')
plt.xlabel('Company Response')
plt.ylabel('Count')
plt.title('Company Response')
plt.show()

#Response across products
df[['Product', 'Timely response?']].value_counts().head().plot(kind='barh', stacked=True)
plt.xlabel('Product')
plt.ylabel('Count')
plt.title('Response across products')

#Timely response across compliant issue
df[['Issue_Category', 'Timely response?']].value_counts().head().plot(kind='barh', stacked=True)
plt.xlabel('Issue')
plt.ylabel('Count')
plt.title('Timely response across compliant issue')

#Complaint Processing Lag Analysis
#Submitted date: The date CFPB received the complaint
#Received Date:The date the CFPB sent the complaint to the company
#Processing lag is the difference between date subitted and date received.
#Values of processing lag
print(df['Processing lag'].max())
print(df['Processing lag'].min())
print(df['Processing lag'].mean())
print(df['Processing lag'].median())
print(df['Processing lag'].quantile(0.90))

#Exermine the distribution of processing lag
#No outliers
df['Processing lag'].value_counts()

#Compare processing lag by submission channel.
sns.boxplot(data = df, x='Submitted via', y='Processing lag')
plt.xlabel('Channel')
plt.ylabel('Processing lag')
plt.title('Processing lag by submission channel')

#Compare processing lag by product.
sns.boxplot(data = df, x='Product', y='Processing lag')
plt.xlabel('Product')
plt.ylabel('Processing lag')
plt.title('Processing lag by product')

#Relationship Analysis
#Product and response outcome
#Company response did not vary across product as more than 90% of complains were resolved and extremely few are still pending.
plt.figure(figsize=(7, 4))
reponse = pd.crosstab(df['Product'], df['Company response to consumer'])
sns.heatmap(reponse, annot=True, fmt='d', cmap='Blues')
plt.title('Product vs Response')
plt.show()

#Issue and timely response
#All products have a large number of timely response with over 90%
percent = pd.crosstab(df['Issue_Category'], df['Timely response?'],
                      normalize = 'index')*100

count = pd.crosstab(df['Issue_Category'], df['Timely response?'])

tabular= count.astype(str) + '(' + percent.round(2).astype(str) + '%' + ')'

tabular

df['processing_lag'] = df['Processing lag'].astype(int)
df['processing_lag'].hist()


#Submission channel and processing lag
pd.crosstab(df['Submitted via'], df['Processing lag'], normalize='index')*100
plt.figure(figsize=(6, 4))
sns.boxplot(data = df, x='Submitted via', y='processing_lag')
plt.xlabel('Channel')
plt.ylabel('Processing lag')
plt.title('lag via submission channel')

pd.crosstab(df['Submitted via'], df['Processing lag'], normalize='index')*100

#Product and complaint month
pd.crosstab(df['Month_name'],df['Product'], normalize='index')*100
#State and product
pd.crosstab(df['Product'],df['State'])

#Complaint year and response outcome
pd.crosstab(df['Complaint year'], df['Company response to consumer']).plot(kind = 'bar', stacked=True)
df.groupby('Month_name')['Complaint ID'].count().pct_change()*100

#Heatmap on issue category and timely reponse
Product = pd.crosstab(df['Issue_Category'], df['Timely response?'])
sns.heatmap(Product, annot=True, fmt='d', cmap='Blues')
plt.title('Issue category vs Timely Response')
plt.show()
Complains = pd.crosstab(df['Issue_Category'], df['Submitted via'])
plt.figure(figsize=(8, 6))
sns.heatmap(Complains, annot=True, fmt='d', cmap='Blues')
plt.title('Complains vs Submission Channel')
plt.show()

df.head()

df.info()
```
