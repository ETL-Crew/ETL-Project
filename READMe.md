# ELT Project Report
## Amazon Cell Phone Reviews
The goal of this project was to prep data using Extract, Transform, Load (ETL) methodology and gain insights from Amazon.com mobile/cell phones customer reviews from November 24, 2003 – September 27, 2019. Insights are rated scale of 1-5 per individual reviewer and average rating. This dataset focuses on both unlocked and locked carriers, and scoped on ten brands: ASUS, Apple, Google, HUAWEI, Motorola, Nokia, OnePlus, Samsung, Sony, and Xiaomi.

We began the process by extracting the most valuable data points based on an Amazon Standard Identification Number (alphanumeric unique identifier), transforming the dataset and uploading the data into a MongoDB database for further analysis. Below was our process:

### Extract/Data Utilized
The data was received from a user named Griko Nibras on Kaggle.com in the form of two CSV files (https://www.kaggle.com/grikomsn/amazon-cell-phones-reviews). The items.csv contains a web scraped read from Amazon.com containing search results of specific brands that has a minimal 1 star review. The reviews.csv contains reviews for previously retrieved items at items.csv but not with columns from items.csv.

### Transformation
Once the two data sets were extracted, the data was transformed using Python and Jupyter Notebooks. A column was dropped from each dataset so only relevant data was left. Removing irrelevant data allowed for increased readability of the files. The following columns were used in in the transformation:

- asin 
- brand 
- titleB_I 
- url 
- image 
- ratingB_I 
- reviewURL 
- totalReviews 
- ratingR 
- date 
- verified
- titleR
- body

Next, six columns we renamed columns from (e.g. 'ratingB_I': 'overall_rating') after we combined the datasets. This was to ensure ease of readability when further analysis is conducted. Lastly, an outer merge was utilized to create one combined file.

### Load
Our data tables were loaded into a MongoDB database. The database allows users to query the curated data tables and draw their own conclusions from the data.

### Next Steps
The next step in the process will be to further analyze the cleaned dataset to identify any trends or patterns that were common among the referenced ten Amazon mobile/cell phones brands over time. 
